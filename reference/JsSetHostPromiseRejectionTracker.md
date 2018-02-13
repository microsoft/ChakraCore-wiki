Sets a callback function that will be called to notify of unhandled Promise Rejections and Rejection Handled events as per ECMASpec #sec-host-promise-rejection-tracker.
### Syntax 
```
CHAKRA_API (JsErrorCode)
    JsSetHostPromiseRejectionTracker(
         _In_ JsHostPromiseRejectionTrackerCallback promiseRejectionTrackerCallback, 
        _In_opt_ void *callbackState);
```
### Parameters 
* __promiseRejectionTrackerCallback__: The callback function being set.
* __callbackState__:  User provided state that will be passed back to the callback.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
Sets whether any action should be taken when a promise is rejected with no reactions
or a reaction is added to a promise that was rejected before it had reactions.
By default in either of these cases nothing occurs.
This function allows you to specify if something should occur and provide a callback
to implement whatever should occur.

Requires an active script context.