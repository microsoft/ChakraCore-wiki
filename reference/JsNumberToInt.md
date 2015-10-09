Retrieves the **int** value of a number value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsNumberToInt(
    _In_ JsValueRef value,
    _Out_ int *intValue);
```
### Parameters 
* __value__: The number value to convert to an **int** value.
* __intValue__: The **int** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
This function retrieves the value of a number value and converts to an **int** value.
It will fail with **JsErrorInvalidArgument** if the type of the value is not number.
