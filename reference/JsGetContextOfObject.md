Gets the script context that the object belongs to. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetContextOfObject(
        _In_ JsValueRef object,
        _Out_ JsContextRef *context);
```
### Parameters 
* __object__: The object to get the context from.
* __context__: The context the object belongs to.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
