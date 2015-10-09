Sets a promise continuation callback function that is called by the context when a task needs to be queued for future execution 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetPromiseContinuationCallback(
    _In_ JsPromiseContinuationCallback promiseContinuationCallback,
    _In_opt_ void *callbackState);
```
### Parameters 
* __promiseContinuationCallback__: The callback function being set.
* __callbackState__:  User provided state that will be passed back to the callback.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
