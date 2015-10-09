Creates a Javascript array object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateArray(
    _In_ unsigned int length,
    _Out_ JsValueRef *result);
```
### Parameters 
* __length__: The initial length of the array.
* __result__: The new array object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
