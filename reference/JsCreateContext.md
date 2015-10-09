Creates a script context for running scripts. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateContext(
    _In_ JsRuntimeHandle runtime,
    _Out_ JsContextRef *newContext);
```
### Parameters 
* __runtime__: The runtime the script context is being created in.
* __newContext__: The created script context.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Each script context has its own global object that is isolated from all other script
contexts.
