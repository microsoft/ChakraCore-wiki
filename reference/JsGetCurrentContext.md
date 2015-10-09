Gets the current script context on the thread. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetCurrentContext(
    _Out_ JsContextRef *currentContext);
```
### Parameters 
* __currentContext__:  The current script context on the thread, null if there is no current script context.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
