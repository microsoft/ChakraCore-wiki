Compare two JavaScript values for strict equality. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsStrictEquals(
    _In_ JsValueRef object1,
    _In_ JsValueRef object2,
    _Out_ bool *result);
```
### Parameters 
* __object1__: The first object to compare.
* __object2__: The second object to compare.
* __result__: Whether the values are strictly equal.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
This function is equivalent to the **===** operator in Javascript.
Requires an active script context.
