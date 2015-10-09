An error code returned from a Chakra hosting API.
### Syntax 
```
enum JsErrorCode : unsigned int
```
### Members 
* __JsNoError__: Success error code.
* __JsErrorCategoryUsage__: Category of errors that relates to incorrect usage of the API itself.
* __JsErrorInvalidArgument__: An argument to a hosting API was invalid.
* __JsErrorNullArgument__: An argument to a hosting API was null in a context where null is not allowed.
* __JsErrorNoCurrentContext__: The hosting API requires that a context be current, but there is no current context.
* __JsErrorInExceptionState__: The engine is in an exception state and no APIs can be called until the exception is
* __JsErrorNotImplemented__: A hosting API is not yet implemented.
* __JsErrorWrongThread__: A hosting API was called on the wrong thread.
* __JsErrorRuntimeInUse__:  A runtime that is still in use cannot be disposed.
* __JsErrorBadSerializedScript__: A bad serialized script was used, or the serialized script was serialized by a different version of the Chakra engine.
* __JsErrorInDisabledState__: The runtime is in a disabled state.
* __JsErrorCannotDisableExecution__: Runtime does not support reliable script interruption.
* __JsErrorHeapEnumInProgress__: A heap enumeration is currently underway in the script context.
* __JsErrorArgumentNotObject__: A hosting API that operates on object values was called with a non-object value.
* __JsErrorInProfileCallback__: A script context is in the middle of a profile callback.
* __JsErrorInThreadServiceCallback__: A thread service callback is currently underway.
* __JsErrorCannotSerializeDebugScript__: Scripts cannot be serialized in debug contexts.
* __JsErrorAlreadyDebuggingContext__: The context cannot be put into a debug state because it is already in a debug state.
* __JsErrorAlreadyProfilingContext__: The context cannot start profiling because it is already profiling.
* __JsErrorIdleNotEnabled__: Idle notification given when the host did not enable idle processing.
* __JsCannotSetProjectionEnqueueCallback__: The context did not accept the enqueue callback.
* __JsErrorCannotStartProjection__: Failed to start projection.
* __JsErrorInObjectBeforeCollectCallback__: The operation is not supported in an object before collect callback.
* __JsErrorObjectNotInspectable__: Object cannot be unwrapped to IInspectable pointer.
* __JsErrorPropertyNotSymbol__: A hosting API that operates on symbol property ids but was called with a non-symbol property id. The error code is returned by JsGetSymbolFromPropertyId if the function is called with non-symbol property id.
* __JsErrorPropertyNotString__: A hosting API that operates on string property ids but was called with a non-string property id. The error code is returned by existing JsGetPropertyNamefromId if the function is called with non-string property id.
* __JsErrorCategoryEngine__: Category of errors that relates to errors occurring within the engine itself.
* __JsErrorOutOfMemory__: The Chakra engine has run out of memory.
* __JsErrorCategoryScript__: Category of errors that relates to errors in a script.
* __JsErrorScriptException__: A JavaScript exception occurred while running a script.
* __JsErrorScriptCompile__: JavaScript failed to compile.
* __JsErrorScriptTerminated__: A script was terminated due to a request to suspend a runtime.
* __JsErrorScriptEvalDisabled__: A script was terminated because it tried to use <c>eval</c> or <c>function</c> and eval was disabled.
* __JsErrorCategoryFatal__: Category of errors that are fatal and signify failure of the engine.
* __JsErrorFatal__: A fatal error in the engine has occurred.
* __JsErrorWrongRuntime__: A hosting API was called with object created on different javascript runtime.
