Returns a value that indicates whether an object is extensible or not. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetExtensionAllowed(
    _In_ JsValueRef object,
    _Out_ bool *value);
```
### Parameters 
* __object__: The object to test.
* __value__: Whether the object is extensible or not.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
