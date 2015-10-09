Retrieves the **bool** value of a Boolean value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsBooleanToBool(
    _In_ JsValueRef value,
    _Out_ bool *boolValue);
```
### Parameters 
* __value__: The value to be converted.
* __boolValue__: The converted value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
