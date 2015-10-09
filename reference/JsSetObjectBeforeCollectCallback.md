Sets a callback function that is called by the runtime before garbage collection of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetObjectBeforeCollectCallback(
    _In_ JsRef ref,
    _In_opt_ void *callbackState,
    _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback);
```
### Parameters 
* __ref__: The object for which to register the callback.
* __callbackState__:  User provided state that will be passed back to the callback.
* __objectBeforeCollectCallback__: The callback function being set. Use null to clear previously registered callback.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
The callback is invoked on the current runtime execution thread, therefore execution is
blocked until the callback completes.
