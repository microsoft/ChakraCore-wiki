Creates a string value from a string pointer. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsPointerToString(
    _In_reads_(stringLength) const wchar_t *stringValue,
    _In_ size_t stringLength,
    _Out_ JsValueRef *value);
```
### Parameters 
* __stringValue__: The string pointer to convert to a string value.
* __stringLength__: The length of the string to convert.
* __value__: The new string value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
