Retrieves the **double** value of a number value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsNumberToDouble(
    _In_ JsValueRef value,
    _Out_ double *doubleValue);
```
### Parameters 
* __value__: The number value to convert to a **double** value.
* __doubleValue__: The **double** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
This function retrieves the value of a number value. It will fail with
**JsErrorInvalidArgument** if the type of the value is not number.
