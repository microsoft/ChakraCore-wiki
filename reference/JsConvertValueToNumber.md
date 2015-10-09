Converts the value to number using standard JavaScript semantics. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsConvertValueToNumber(
    _In_ JsValueRef value,
    _Out_ JsValueRef *numberValue);
```
### Parameters 
* __value__: The value to be converted.
* __numberValue__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
