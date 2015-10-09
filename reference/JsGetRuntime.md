Gets the runtime that the context belongs to. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetRuntime(
    _In_ JsContextRef context,
    _Out_ JsRuntimeHandle *runtime);
```
### Parameters 
* __context__: The context to get the runtime from.
* __runtime__: The runtime the context belongs to.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
