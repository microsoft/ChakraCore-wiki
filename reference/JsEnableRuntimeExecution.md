Enables script execution in a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsEnableRuntimeExecution(
    _In_ JsRuntimeHandle runtime);
```
### Parameters 
* __runtime__: The runtime to be enabled.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Enabling script execution in a runtime that already has script execution enabled is a
no-op.
