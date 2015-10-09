Creates a Boolean value from a **bool** value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsBoolToBoolean(
    _In_ bool value,
    _Out_ JsValueRef *booleanValue);
```
### Parameters 
* __value__: The value to be converted.
* __booleanValue__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
