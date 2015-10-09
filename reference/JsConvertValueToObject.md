Converts the value to object using standard JavaScript semantics. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsConvertValueToObject(
    _In_ JsValueRef value,
    _Out_ JsValueRef *object);
```
### Parameters 
* __value__: The value to be converted.
* __object__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
