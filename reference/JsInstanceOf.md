Performs JavaScript "instanceof" operator test. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsInstanceOf(
    _In_ JsValueRef object,
    _In_ JsValueRef constructor,
    _Out_ bool *result);
```
### Parameters 
* __object__: The object to test.
* __constructor__: The constructor function to test against.
* __result__: Whether "object instanceof constructor" is true.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
