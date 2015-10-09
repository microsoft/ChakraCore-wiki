Delete the value at the specified index of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDeleteIndexedProperty(
    _In_ JsValueRef object,
    _In_ JsValueRef index);
```
### Parameters 
* __object__: The object to operate on.
* __index__: The index to delete.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
