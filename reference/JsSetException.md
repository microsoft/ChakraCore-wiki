Sets the runtime of the current context to an exception state. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetException(
    _In_ JsValueRef exception);
```
### Parameters 
* __exception__:  The JavaScript exception to set for the runtime of the current context.

### Return Value 
JsNoError if the engine was set into an exception state, a failure code otherwise.
### Remarks 
If the runtime of the current context is already in an exception state, this API will
return **JsErrorInExceptionState**.
Requires an active script context.
