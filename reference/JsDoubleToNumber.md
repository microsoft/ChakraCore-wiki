Creates a number value from a **double** value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDoubleToNumber(
    _In_ double doubleValue,
    _Out_ JsValueRef *value);
```
### Parameters 
* __doubleValue__: The **double** to convert to a number value.
* __value__: The new number value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
