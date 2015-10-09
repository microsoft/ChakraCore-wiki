Creates a new JavaScript SyntaxError error object 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateSyntaxError(
    _In_ JsValueRef message,
    _Out_ JsValueRef *error);
```
### Parameters 
* __message__: Message for the error object.
* __error__: The new error object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
