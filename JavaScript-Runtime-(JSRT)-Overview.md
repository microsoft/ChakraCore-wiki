The JavaScript Runtime (JSRT) APIs provide a way to embed ChakraCore into applications and light up JavaScript capabilities. JSRT APIs are shipped as part of the ChakraCore project. This document describes the key concepts and aspects of JSRT APIs. For API reference, please see [[JavaScript Runtime (JSRT) Reference]]. 

## Concepts

Understanding how to host the JavaScript engine using the JSRT APIs depends on two key concepts: **runtimes** and **execution contexts**.

A **runtime** represents a complete JavaScript execution environment. Each runtime that is created has its own isolated garbage collected heap and, by default, its own just-in-time (JIT) compiler thread and garbage collector (GC) thread. An execution context represents a JavaScript environment that has its own JavaScript global object distinct from all other execution contexts. One runtime may contain multiple execution contexts, and in such cases, all the execution contexts share the JIT compiler and GC thread associated with the runtime. 

Runtimes represent a single thread of execution. Only one runtime can be active on a particular thread at a time, and a runtime can only be active on one thread at a time. Runtimes are rental threaded, so a runtime that is not currently active on a thread (i.e. isn’t running any JavaScript code or responding to any calls from the host) can be used on any thread that doesn’t already have an active runtime on it.

**Execution contexts** are tied to a particular runtime and execute code within that runtime. Unlike runtimes, multiple execution contexts can be active on a thread at the same time. So a host can make a call into an execution context, that execution context can call back to the host, and the host can make a call into a different execution context.

[[/images/context.png]]

In practice, unless a host needs to run code in separated environments, a single execution context can be used. Similarly, unless a host needs to run multiple pieces of code concurrently, a single runtime is sufficient.

## Memory management
JavaScript is a garbage collected language, and thus there are several considerations that must be kept in mind when working with the JSRT APIs from another language.

The main consideration is that the JavaScript garbage collector can only see references to values in two places: its runtime’s heap, and the stack. Thus, a reference to a JavaScript value that is stored inside of another JavaScript value or in a local variable on the stack will always be seen by the garbage collector. But references stored in other locations, such as heaps managed by the host or the system, will not be seen by the garbage collector and may result in premature collection of values that are still in use by the host.
 
If a reference to a JavaScript value will be stored in a location not visible to the garbage collector, the host must manually add and remove references using the JSRT APIs.

## Exception handling
When a JavaScript exception occurs during script execution, the containing runtime is put into an exception state. While in an exception state, no code can run and all API calls will fail with the error code **JsErrorInExceptionState** until the host retrieves and clears the exception using the **JsGetAndClearException** API. If the host returns from a JavaScript callback without clearing the runtime from an exception state, then the JavaScript exception will be re-thrown as soon as control passes back to the JavaScript engine. This also enables host callbacks to “throw” a JavaScript exception by setting the runtime into an exception state and then returning from a host callback.

A host is not allowed to let its own internal exceptions to propagate across a host callback—any callback methods must catch all host exceptions before returning control to the runtime.

## Runtime resource usage
The JSRT APIs expose a number of way to monitor and modify the way runtimes use resources. They generally break down into the following categories:

* **Thread Usage**. By default, each runtime will create a dedicated JIT compiler thread and a dedicated GC thread that service that runtime. If a runtime is created with the **JsRuntimeAttributeDisableBackgroundWork** flag, then the JIT and GC work will be performed on the runtime thread itself instead of separate background threads for each one of them. A host can also supply a thread service callback to the **JsCreateRuntime** call, which will allow the host to schedule JIT and GC work in any way it sees fit.


* **Memory Usage**. There are several ways to monitor and modify the memory usage of a runtime. If the runtime will be running for a long time, the host can specify the **JsRuntimeAttributeEnableIdleProcessing** flag when creating the runtime and then call **JsIdle** when the host is in an idle state. This allows the engine to defer some memory cleanup and bookkeeping work until idle time.

    The host can monitor garbage collections by calling **JsSetRuntimeBeforeCollectCallback**. It can also monitor allocations made by the heap by calling **JsSetRuntimeMemoryAllocationCallback**. Note that this API does not call back on every JavaScript allocation, just when the runtime’s heap needs more space from which to allocate. The memory allocation callback is allowed to deny the request, which will trigger a garbage collection and, if no memory is available, an out of memory error in the runtime.

    The host can also call **JsSetRuntimeMemoryLimit** to set a limit for how much memory a runtime can use. When a runtime hits a limit, it will trigger a garbage collection and, if no memory is available, an out of memory error will be thrown by the runtime.

* **Script Interruption and Evaluation**. The host can call **JsDisableRuntimeExecution** to terminate execution within a runtime. This call can be made at any time and from any thread. Because script termination depends on reaching guard points inserted into the code, a script may not terminate at the exact moment, but will do so very shortly afterwards. By default, termination guard points are placed in the generated code conservatively and may not cover every situation, such as an infinite loop. Creating the runtime with the **JsRuntimeAttributeAllowScriptInterrupt** flag causes the runtime to insert additional checks for infinite loops, often at the cost of a small performance overhead.

    If a host wishes to disallow generation of native code by the JIT compiler, it can specify the **JsRuntimeAttributeDisableNativeCodeGeneration** flag. A host can also disallow scripts from dynamically running scripts itself by specifying the **JsRuntimeAttributeDisableEval** flag.

## Debugging
We are working on providing debugging functionalitiles. 

## Promises
An embedding application needs to provide an EnqueueJob abstract operation to queue up the promise tasks before promises can be used. **JsSetPromiseContinuationCallback** allows application to provide an EnqueueJob style callback to process the promise task queue. The following sample shows how to store the promise tasks in a queue and execute them after the current execution context is finished:
```
void CALLBACK PromiseContinuationCallback(JsValueRef task, void *callbackState)
{
    // Save promise task in taskQueue.
    queue<JsValueRef> * q = (queue<JsValueRef> *)callbackState;
    q->push(task);
}

void runPromiseSample()
{
    queue<JsValueRef> taskQueue;  
    JsValueRef result;
    JsSetPromiseContinuationCallback(PromiseContinuationCallback, &taskQueue);
    JsRunScript(
        L"//The JavaScript ES6 Promise code goes here" \
        L"new Promise(" \
        L" function(resolve, reject) {resolve('basic:success');}" \
        L").then(function () {return new Promise(" \
        L" function(resolve, reject) {resolve('second:success')}" \
        L")});", JS_SOURCE_CONTEXT_NONE, L"", &result);
		
    JsValueRef global;
    JsGetGlobalObject(&global);

    // Execute promise tasks stored in taskQueue
    while (!taskQueue.empty()) {
        JsValueRef task = taskQueue.front();
        taskQueue.pop();
        JsCallFunction(task, &global, 1, &result);
    }
}
```
All other supported ES2015 features do not require any setup to run in JSRT. 

## Experimental Features
Experimental JavaScript features that are not yet stable are hidden behind an experimental flag. You can enable these features on a runtime by specifying **JsRuntimeAttributeEnableExperimentalFeatures** flag when **JsCreateRuntime** is called. 

## Resources
* [[JavaScript Runtime (JSRT) Reference]]
* [JSRT and ChakraCore Samples](http://aka.ms/chakracoresamples)