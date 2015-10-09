Determines whether the runtime of the current context is in an exception state. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasException(
    _Out_ bool *hasException);
```
### Parameters 
* __hasException__:  Whether the runtime of the current context is in the exception state.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
If a call into the runtime results in an exception (either as the result of running a
script or due to something like a conversion failure), the runtime is placed into an
"exception state." All calls into any context created by the runtime (except for the
exception APIs) will fail with **JsErrorInExceptionState** until the exception is
cleared.
If the runtime of the current context is in the exception state when a callback returns
into the engine, the engine will automatically rethrow the exception.
Requires an active script context.
