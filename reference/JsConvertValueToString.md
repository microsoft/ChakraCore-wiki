Converts the value to string using standard JavaScript semantics. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsConvertValueToString(
    _In_ JsValueRef value,
    _Out_ JsValueRef *stringValue);
```
### Parameters 
* __value__: The value to be converted.
* __stringValue__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
