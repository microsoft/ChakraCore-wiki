Attributes of a runtime.
### Syntax 
```
enum JsRuntimeAttributes
```
### Members 
* __JsRuntimeAttributeNone__: No special attributes.
* __JsRuntimeAttributeDisableBackgroundWork__: The runtime will not do any work (such as garbage collection) on background threads.
* __JsRuntimeAttributeAllowScriptInterrupt__: The runtime should support reliable script interruption. This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.
* __JsRuntimeAttributeEnableIdleProcessing__: Host will call <c>JsIdle</c>, so enable idle processing. Otherwise, the runtime will manage memory slightly more aggressively.
* __JsRuntimeAttributeDisableNativeCodeGeneration__: Runtime will not generate native code.
* __JsRuntimeAttributeDisableEval__: Using **eval** or **function** constructor will throw an exception.
* __JsRuntimeAttributeEnableExperimentalFeatures__: Runtime will enable all experimental features.
* __JsRuntimeAttributeDispatchSetExceptionsToDebugger__: Calling **JsSetException** will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.
