Determine if one JavaScript value is less than another JavaScript value.
### Syntax
```
CHAKRA_API
    JsLessThan(
        _In_ JsValueRef object1,
        _In_ JsValueRef object2,
        _Out_ bool *result);
```
### Parameters
* __object1__: The first object to compare.
* __object2__: The second object to compare.
* __result__: Whether object1 is less than object2.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks
Requires an active script context.

This function is equivalent to the **\<** operator in Javascript.
