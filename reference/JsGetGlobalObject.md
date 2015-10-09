Gets the global object in the current script context. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetGlobalObject(
    _Out_ JsValueRef *globalObject);
```
### Parameters 
* __globalObject__: The global object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
