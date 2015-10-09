Set the value at the specified index of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetIndexedProperty(
    _In_ JsValueRef object,
    _In_ JsValueRef index,
    _In_ JsValueRef value);
```
### Parameters 
* __object__: The object to operate on.
* __index__: The index to set.
* __value__: The value to set.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
