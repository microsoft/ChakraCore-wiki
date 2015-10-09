Retrieve the value at the specified index of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetIndexedProperty(
    _In_ JsValueRef object,
    _In_ JsValueRef index,
    _Out_ JsValueRef *result);
```
### Parameters 
* __object__: The object to operate on.
* __index__: The index to retrieve.
* __result__: The retrieved value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
