Returns a value that indicates whether script execution is disabled in the runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsIsRuntimeExecutionDisabled(
    _In_ JsRuntimeHandle runtime,
    _Out_ bool *isDisabled);
```
### Parameters 
* __runtime__: Specifies the runtime to check if execution is disabled.
* __isDisabled__: If execution is disabled, **true**, **false** otherwise.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
