Tests whether an object has a value at the specified index. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasIndexedProperty(
    _In_ JsValueRef object,
    _In_ JsValueRef index,
    _Out_ bool *result);
```
### Parameters 
* __object__: The object to operate on.
* __index__: The index to test.
* __result__: Whether the object has an value at the specified index.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
