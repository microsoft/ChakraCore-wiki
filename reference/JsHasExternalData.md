Determines whether an object is an external object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasExternalData(
    _In_ JsValueRef object,
    _Out_ bool *value);
```
### Parameters 
* __object__: The object.
* __value__: Whether the object is an external object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
