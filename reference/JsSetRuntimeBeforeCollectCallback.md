Sets a callback function that is called by the runtime before garbage collection. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetRuntimeBeforeCollectCallback(
    _In_ JsRuntimeHandle runtime,
    _In_opt_ void *callbackState,
    _In_ JsBeforeCollectCallback beforeCollectCallback);
```
### Parameters 
* __runtime__: The runtime for which to register the allocation callback.
* __callbackState__:  User provided state that will be passed back to the callback.
* __beforeCollectCallback__: The callback function being set.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
The callback is invoked on the current runtime execution thread, therefore execution is
blocked until the callback completes.
The callback can be used by hosts to prepare for garbage collection. For example, by
releasing unnecessary references on Chakra objects.
