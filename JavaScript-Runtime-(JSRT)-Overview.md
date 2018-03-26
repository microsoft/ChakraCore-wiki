The JavaScript Runtime (JSRT) APIs provide a way to embed ChakraCore into applications and light up JavaScript capabilities. JSRT APIs are shipped as part of the ChakraCore project. This document describes the key concepts and aspects of JSRT APIs. For API reference, please see [[JavaScript Runtime (JSRT) Reference]]. 

## Concepts

Understanding how to host the JavaScript engine using the JSRT APIs depends on two key concepts: **runtimes** and **execution contexts**.

A **runtime** represents a complete JavaScript execution environment. Each runtime that is created has its own isolated garbage-collected heap and, by default, its own just-in-time (JIT) compiler thread and garbage collector (GC) thread. An execution context represents a JavaScript environment that has its own JavaScript global object distinct from all other execution contexts. One runtime may contain multiple execution contexts, and in such cases, all the execution contexts share the JIT compiler and GC thread associated with the runtime. 

Runtimes represent a single thread of execution. Only one runtime can be active on a particular thread at a time, and a runtime can only be active on one thread at a time. Runtimes are rental threaded, so a runtime that is not currently active on a thread (i.e. isn’t running any JavaScript code or responding to any calls from the host) can be used on any thread that doesn’t already have an active runtime on it.

**Execution contexts** are tied to a particular runtime and execute code within that runtime. Unlike runtimes, multiple execution contexts can be active on a thread at the same time. So a host can make a call into an execution context, that execution context can call back to the host, and the host can make a call into a different execution context.

[[/images/context.png]]

In practice, unless a host needs to run code in separated environments, a single execution context can be used. Similarly, unless a host needs to run multiple pieces of code concurrently, a single runtime is sufficient.

Contexts are collectible by GC, as long as they are not set as the current context on the runtime or have a positive reference count (more times calling **JsAddRef** than **JsRelease**).

## Memory management
JavaScript is a garbage collected language, and thus there are several considerations that must be kept in mind when working with the JSRT APIs from another language.

The main consideration is that the JavaScript garbage collector can only see references to values in two places: its runtime’s heap, and the stack. Thus, a reference to a JavaScript value that is stored inside of another JavaScript value or in a local variable on the stack will always be seen by the garbage collector. But references stored in other locations, such as heaps managed by the host or the system, will not be seen by the garbage collector and may result in premature collection of values that are still in use by the host. If a reference to a JavaScript value will be stored in a location not visible to the garbage collector, the host must manually add and remove references using **JsAddRef** and **JsRelease**.

If ChakraCore is hosted in a managed environment, special care needs to be taken as two GCs do not necessarily understand each other. With .NET, any delegate passed to ChakraCore needs to be pinned or else can be prematurely collected by .NET GC. 

## Exception handling
When a JavaScript exception occurs during script execution, the containing runtime is put into an exception state. While in an exception state, no code can run and all API calls will fail with the error code **JsErrorInExceptionState** until the host retrieves and clears the exception using the **JsGetAndClearException** API, which returns an **exception** object with a **message** property indicating the error message. If the host returns from a JavaScript callback without clearing the runtime from an exception state, then the JavaScript exception will be re-thrown as soon as control passes back to the JavaScript engine. This also enables host callbacks to “throw” a JavaScript exception by setting the runtime into an exception state and then returning from a host callback.

A host is not allowed to let its own internal exceptions to propagate across a host callback—any callback methods must catch all host exceptions before returning control to the runtime.

## Runtime resource usage
The JSRT APIs expose a number of ways to monitor and modify the way runtimes use resources. They generally break down into the following categories:

* **Thread Usage**. By default, each runtime will create a dedicated JIT compiler thread and a dedicated GC thread that service that runtime. If a runtime is created with the **JsRuntimeAttributeDisableBackgroundWork** flag, then the JIT and GC work will be performed on the runtime thread itself instead of separate background threads for each one of them. A host can also supply a thread service callback to the **JsCreateRuntime** call, which will allow the host to schedule JIT and GC work in any way it sees fit.


* **Memory Usage**. There are several ways to monitor and modify the memory usage of a runtime. If the runtime will be running for a long time, the host can specify the **JsRuntimeAttributeEnableIdleProcessing** flag when creating the runtime and then call **JsIdle** when the host is in an idle state. This allows the engine to defer some memory cleanup and bookkeeping work until idle time.

    The host can monitor garbage collections by calling **JsSetRuntimeBeforeCollectCallback**. It can also monitor allocations made by the heap by calling **JsSetRuntimeMemoryAllocationCallback**. Note that this API does not call back on every JavaScript allocation, just when the runtime’s heap needs more space from which to allocate. The memory allocation callback is allowed to deny the request, which will trigger a garbage collection and, if no memory is available, an out of memory error in the runtime.

    The host can also call **JsSetRuntimeMemoryLimit** to set a limit for how much memory a runtime can use. When a runtime hits a limit, it will trigger a garbage collection and, if no memory is available, an out of memory error will be thrown by the runtime.

* **Script Interruption and Evaluation**. The host can call **JsDisableRuntimeExecution** to terminate execution within a runtime. This call can be made at any time and from any thread. Because script termination depends on reaching guard points inserted into the code, a script may not terminate at the exact moment, but will do so very shortly afterwards. By default, termination guard points are placed in the generated code conservatively and may not cover every situation, such as an infinite loop. Creating the runtime with the **JsRuntimeAttributeAllowScriptInterrupt** flag causes the runtime to insert additional checks for infinite loops, often at the cost of a small performance overhead.

    If a host wishes to disallow generation of native code by the JIT compiler, it can specify the **JsRuntimeAttributeDisableNativeCodeGeneration** flag. A host can also disallow scripts from dynamically running scripts itself by specifying the **JsRuntimeAttributeDisableEval** flag.

## Debugging
To debug scripts with ChakraCore, we expose a set of experimental JSON-based diagnostic [APIs](https://github.com/Microsoft/ChakraCore/blob/master/lib/Jsrt/ChakraDebug.h) for embedders to implement their own debuggers.

## Promises
An embedding application needs to provide an EnqueueJob abstract operation to queue up the promise tasks before promises can be used. **JsSetPromiseContinuationCallback** allows application to provide an EnqueueJob style callback to process the promise task queue. The following sample shows how to store the promise tasks in a queue and execute them after the current execution context is finished:
```
void CALLBACK PromiseContinuationCallback(JsValueRef task, void *callbackState)
{
    // Save promise task in taskQueue.
    queue<JsValueRef> * q = (queue<JsValueRef> *)callbackState;
    q->push(task);
    JsAddRef(task, nullptr);
}

void runPromiseSample()
{
    queue<JsValueRef> taskQueue;  
    JsValueRef result;
    JsSetPromiseContinuationCallback(PromiseContinuationCallback, &taskQueue);
    JsRunScript(
	L"//The JavaScript ES6 Promise code goes here\n" \
	L"new Promise((resolve, reject) => resolve('basic:success'))" \
	L".then(() => {return 'second:success'});", 
	JS_SOURCE_CONTEXT_NONE, L"", &result);
		
    JsValueRef global;
    JsGetGlobalObject(&global);

    // Execute promise tasks stored in taskQueue
    while (!taskQueue.empty()) {
        JsValueRef task = taskQueue.front();
        taskQueue.pop();
        JsCallFunction(task, &global, 1, &result);
        JsRelease(task, nullptr);
    }
}
```
All other supported ES2015 features do not require any setup to run in JSRT. 

Features based on promises, such as [ES2016/ES7 Async Functions](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/), would require setting up promises before usage. 

## Modules
ES6 Modules are supported in ChakraCore. However, the host needs to specify how to resolve a module specifier since this part is host-specific not runtime-related. JSRT provides experimental APIs to set up ES6 modules. This [PR](https://github.com/Microsoft/ChakraCore/pull/1254) gives you an overview of the related APIs and an example implementation (see WScriptJsrt.cpp) in the ch test host. Better documentation will be provided in the future.

## Experimental Features
Experimental JavaScript features that are not yet stable are hidden behind an experimental flag. You can enable these features on a runtime by specifying **JsRuntimeAttributeEnableExperimentalFeatures** flag when **JsCreateRuntime** is called. 

## Basic tasks

This section aims to illustrate how to achieve a few common tasks with JSRT with code samples.

### Expose native functions/objects to JavaScript

The basic idea is to create a native function or (external) object, and expose it to JS by setting it as a property of an object JS is already aware of. For example, let's expose `console.log`, which many JavaScript hosts expose but isn't part of JavaScript.

```cpp
// a native function for logging
JsValueRef CALLBACK LogCB(JsValueRef callee, bool isConstructCall, JsValueRef *arguments, unsigned short argumentCount, void *callbackState)
{
    for (unsigned int index = 1; index < argumentCount; index++)
    {
        if (index > 1)
        {
            printf(" ");
        }
        JsValueRef stringValue;
        JsConvertValueToString(arguments[index], &stringValue);
        char *string = nullptr;
        size_t length;
        JsCopyString(stringValue, nullptr, 0, &length);
        string = (char*)malloc(length + 1);
        JsCopyString(stringValue, string, length+1, nullptr);
        printf("%s", string);
    }
    printf("\n");
    return JS_INVALID_REFERENCE;
}

JsValueRef console, logFunc, global;
JsPropertyIdRef consolePropId, logPropId;
const char* logString = "log";
const char* consoleString = "console";
// create console object, log function, and set log function as property of console
JsCreateObject(&console);
JsCreateFunction(LogCB, nullptr, &logFunc);
JsCreatePropertyId(logString, strlen(logString), &logPropId);
JsSetProperty(console, logPropId, logFunc, true);
// set console as property of global object
JsGetGlobalObject(&global);
JsCreatePropertyId(consoleString, strlen(consoleString), &consolePropId);
JsSetProperty(global, consolePropId, console, true);
```

Now in JavaScript, you can do:

```js
console.log('Hello world');
```

You can also create external objects that host data not directly exposed to JS via `JsCreateExternalObject` or `JsCreateExternalObjectWithPrototype`.

```cpp
// creates an external object holding an int
JsValueRef null, extObj;
JsGetNullValue(&null);
int data = 0;
JsCreateExternalObjectWithPrototype(&data, nullptr, null, &extObj);
```

You can define native methods on the external object and have access to the external data.

```cpp
// a native method that type casts the external data and adds one.
JsValueRef CALLBACK addOne(JsValueRef callee, bool isConstructCall, JsValueRef *arguments, unsigned short argumentCount, void *callbackState)
{
    void* extData;
    JsGetExternalData(arguments[0], &extData);
    int* data = (int*)(extData);
    *data += 1;
    return JS_INVALID_REFERENCE;
}
```

### Call JavaScript functions from native

You can call JavaScript functions by calling `JsRun/JsRunScript`, or alternatively you can get the native reference of your JS function and then use `JsCallFunction` to call it. For example, to call `func` defined in global scope in JS,

```cpp
JsValueRef func, funcPropId, global, undefined, result;
JsGetGlobalObject(&global);
JsGetUndefinedValue(&undefined);
JsValueRef args[] = { undefined };
const char* funcString = "func";
JsCreatePropertyId(funcString, strlen(funcString), &funcPropId);
JsGetProperty(global, funcPropId, &func);
// note that args[0] is thisArg of the call; actual args start at index 1
JsCallFunction(func, args, 1, &result);
``` 

### Script serialization with lazy source loading  

To support startup and execution efficiency, JSRT APIs provide the capability of pre-parsing, generating syntax trees and caching the bytecode for scripts. It is especially useful for server scenarios where the same script could get executed thousands of times.

The basic idea is to use variants of `JsSerializeScript` to parse and store the bytecode and then use variants of `JsRunSerialized` to parse or run the bytecode. Source is typically not needed for running serialized code, therefore you can also lazy-load the source script using `JsRunSerialized/JsRunSerializedScriptWithCallback`.

```cpp
// serialize script
void serializeScript(char* scriptPath, char* script) {
    JsValueRef scriptSource, bytecodeBuffer;
    JsCreateExternalArrayBuffer((void*)script, (unsigned int)strlen(script), nullptr, nullptr, &scriptSource);
    JsSerialize(scriptSource, &bytecodeBuffer, JsParseScriptAttributeNone);
    JsAddRef(bytecodeBuffer, nullptr);
    SerializedSourceContext* context = new SerializedSourceContext();
    context->script = script;
    context->scriptPath = scriptPath;
    context->bytecodeBuffer = bytecodeBuffer;
    bytecodeStore[scriptPath] = context;
}

// load and run bytecode 
void runSerializeScript(char* scriptPath) {
    JsValueRef result;
    SerializedSourceContext* context = bytecodeStore[scriptPath];
    JsRunSerialized(
        context->bytecodeBuffer, 
        [](JsSourceContext sourceContext, JsValueRef* scriptBuffer, JsParseScriptAttributes* parseAttributes) 
        {
            SerializedSourceContext* scontext = reinterpret_cast<SerializedSourceContext*>(sourceContext);
            if (scontext->script == nullptr) {
                scontext->script = LoadScript(scontext->scriptPath);
            }
            scriptBuffer = scontext->script;
            *parseAttributes = JsParseScriptAttributeNone;
            return true;
        },
        (JsSourceContext)context,
        nullptr,
        &result
    );
}
```

## Resources
* [[JavaScript Runtime (JSRT) Reference]]
* [JSRT and ChakraCore Samples](https://github.com/Microsoft/Chakra-Samples)