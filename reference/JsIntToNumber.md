Creates a number value from an **int** value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsIntToNumber(
    _In_ int intValue,
    _Out_ JsValueRef *value);
```
### Parameters 
* __intValue__: The **int** to convert to a number value.
* __value__: The new number value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
