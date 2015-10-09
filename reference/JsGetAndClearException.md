Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetAndClearException(
    _Out_ JsValueRef *exception);
```
### Parameters 
* __exception__: The exception for the runtime of the current context.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
If the runtime of the current context is not in an exception state, this API will return
**JsErrorInvalidArgument**. If the runtime is disabled, this will return an exception
indicating that the script was terminated, but it will not clear the exception (the
exception will be cleared if the runtime is re-enabled using
**JsEnableRuntimeExecution**).
Requires an active script context.
