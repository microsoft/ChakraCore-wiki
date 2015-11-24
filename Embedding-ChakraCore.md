ChakraCore can be embedded via JavaScript Runtime (JSRT) APIs. This document goes through the basics of embedding with a Hello-world sample to get you started. To learn more about JSRT, visit [[JavaScript Runtime (JSRT) Overview]]. 

## Before you start
You should first clone and build [ChakraCore](https://github.com/Microsoft/ChakraCore). There are a few files that you will need,

1. `include` **folder**, which contains the headers. 
2. **CharkaCore.lib** and **ChakraCore.dll** from `Build\VcBuild\bin\[platform+output]\`.

C# users only need **ChakraCore.dll**.  

## Use JSRT with Visual Studio 
To use JSRT in a **C++** project:

1. Copy the **include** folder into your project 
2. `#include "chakracore.h"` in your project.
3. In Visual Studio, go to `<your project> > Properties > Configuration Properties > Linker > Input > Additional Dependencies`, and add a reference to **ChakraCore.lib**. 
4. Copy **ChakraCore.dll** to the project output directory. 

To use JSRT in a **C#** project:

1. Copy **ChakraCore.dll** to the project output directory. 
2. In general, use [PInvoke](https://msdn.microsoft.com/en-us/library/aa288468.aspx) to call JSRT APIs. You can copy a wrapper from our [sample](http://aka.ms/jsrtwrapper). Sometimes, there may be new APIs that we have not yet added to the wrapper, but you can import from **ChakraCore.dll** like this,
```
[DllImport("ChakraCore.dll")] 
internal static extern JavaScriptErrorCode JsCreateRuntime(JavaScriptRuntimeAttributes attributes, JavaScriptThreadServiceCallback threadService, out JavaScriptRuntime runtime); 
```

Alternatively, you can also try using a higher level [JSRT-WinRT WinRT Component](https://github.com/robpaveza/jsrt-winrt#getting-started). 

## Hello World!
A sample to help you understand how to embed ChakraCore with JSRT APIs. For C# users, please refer to the next [section](https://github.com/Microsoft/ChakraCore/wiki/Embedding-ChakraCore#hello-world-c). 

```
#include "chakracore.h"
#include <string>
#include <iostream>

using namespace std;

int main()
{
    JsRuntimeHandle runtime;
    JsContextRef context;
    JsValueRef result;
    unsigned currentSourceContext = 0;

    // Your script; try replace hello-world with something else
    wstring script = L"(()=>{return \'Hello world!\';})()";

    // Create a runtime. 
    JsCreateRuntime(JsRuntimeAttributeNone, nullptr, &runtime);

    // Create an execution context. 
    JsCreateContext(runtime, &context);

    // Now set the current execution context.
    JsSetCurrentContext(context);

    // Run the script.
    JsRunScript(script.c_str(), currentSourceContext++, L"", &result);

    // Convert your script result to String in JavaScript; redundant if your script returns a String
    JsValueRef resultJSString;
    JsConvertValueToString(result, &resultJSString);

    // Project script result back to C++.
    const wchar_t *resultWC;
    size_t stringLength;
    JsStringToPointer(resultJSString, &resultWC, &stringLength);

    wstring resultW(resultWC);
    cout << string(resultW.begin(), resultW.end()) << endl;
    
    return 0;
}
```

To build and run this sample, 

1. Create a new C++ project in Visual Studio, complete the use JSRT with Visual Studio steps, and add the above code to a .cpp file. Alternatively, download this sample [here](http://aka.ms/chakracorehelloworld) and copy **ChakraCore.dll** to project output directory. 
2. In Visual Studio, build the sample by pressing `F6` or using `Build > Build Solution`.
3. Run the sample by pressing `Ctrl+F5` or using `Debug > Start Without Debugging`.

## Hello World! (C#)
C# version of the above Hello-world sample. Note that JSRT APIs are C++ APIs, this sample assumes a C# [wrapper](http://aka.ms/jsrtwrapper). 

```
using System;
using System.Runtime.InteropServices;
// wrapper namespace
using ChakraHost.Hosting;

public class HelloWorld
{
    static void Main() {
        JavaScriptRuntime runtime;
        JavaScriptContext context;
        JavaScriptSourceContext currentSourceContext = JavaScriptSourceContext.FromIntPtr(IntPtr.Zero);
        JavaScriptValue result;

        // Your script, try replace the basic hello world with something else
        string script = "(()=>{return \'Hello world!\';})()";

        // Create a runtime. 
        Native.JsCreateRuntime(JavaScriptRuntimeAttributes.None, null, out runtime);
        
        // Create an execution context. 
        Native.JsCreateContext(runtime, out context);
        
        // Now set the execution context as being the current one on this thread.
        Native.JsSetCurrentContext(context);
        
        // Run the script.
        Native.JsRunScript(script, currentSourceContext++, "", out result);

        // Convert your script result to String in JavaScript; redundant if your script returns a String
        JavaScriptValue resultJSString;
        Native.JsConvertValueToString(result, out resultJSString);
        
        // Project script result in JS back to C#.
        IntPtr resultPtr;
        UIntPtr stringLength;
        Native.JsStringToPointer(resultJSString, out resultPtr, out stringLength);

        string resultString = Marshal.PtrToStringUni(resultPtr);
        Console.WriteLine(resultString);
    }
}
```
To build and run this sample, 

1. Create a new C# project in Visual Studio, complete the use JSRT with Visual Studio steps, include a C# [wrapper](http://aka.ms/jsrtwrapper) for JSRT and add the above code to a .cs file. Alternatively, download this sample [here](http://aka.ms/chakracorecorehelloworldcsharp) and copy **ChakraCore.dll** to project output directory. 
. 
2. In Visual Studio, build the sample by pressing `F6` or using `Build > Build Solution`.
3. Run the sample by pressing `Ctrl+F5` or using `Debug > Start Without Debugging`.

## More on JSRT
* [[JavaScript Runtime (JSRT) Overview]]
* [[JavaScript Runtime (JSRT) Reference]]
* [JSRT and ChakraCore Samples](http://aka.ms/chakracoresamples)