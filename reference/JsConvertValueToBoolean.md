Converts the value to Boolean using standard JavaScript semantics. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsConvertValueToBoolean(
    _In_ JsValueRef value,
    _Out_ JsValueRef *booleanValue);
```
### Parameters 
* __value__: The value to be converted.
* __booleanValue__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
