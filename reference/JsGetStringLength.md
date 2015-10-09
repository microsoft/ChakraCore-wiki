Gets the length of a string value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetStringLength(
    _In_ JsValueRef stringValue,
    _Out_ int *length);
```
### Parameters 
* __stringValue__: The string value to get the length of.
* __length__: The length of the string.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
