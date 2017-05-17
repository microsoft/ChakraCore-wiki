Retrieves the string pointer of a string value. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsStringToPointer(
    _In_ JsValueRef value,
    _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,
    _Out_ size_t *stringLength);
```
### Parameters 
* __value__: The string value to convert to a string pointer.
* __stringValue__: The string pointer.
* __stringLength__: The length of the string.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
This API is Windows-only (see [[JsCopyString]]/[[JsCopyStringUtf16]] for cross-platform equivalent).
This function retrieves the string pointer of a string value. It will fail with
**JsErrorInvalidArgument** if the type of the value is not string. The lifetime
of the string returned will be the same as the lifetime of the value it came from, however
the string pointer is not considered a reference to the value (and so will not keep it
from being collected).
Requires an active script context.
