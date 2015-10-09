Suspends script execution and terminates any running scripts in a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDisableRuntimeExecution(
    _In_ JsRuntimeHandle runtime);
```
### Parameters 
* __runtime__: The runtime to be suspended.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Calls to a suspended runtime will fail until **JsEnableRuntimeExecution** is called.
This API does not have to be called on the thread the runtime is active on. Although the
runtime will be set into a suspended state, an executing script may not be suspended
immediately; a running script will be terminated with an uncatchable exception as soon as
possible.
Suspending execution in a runtime that is already suspended is a no-op.
