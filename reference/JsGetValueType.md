taView = 12, eType; Gets the JavaScript type of a JsValueRef. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetValueType(
    _In_ JsValueRef value,
    _Out_ JsValueType *type);
```
### Parameters 
* __value__: The value whose type is to be returned.
* __type__: The type of the value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
