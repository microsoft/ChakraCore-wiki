A Promise Rejection Tracker callback.
### Syntax 
```
typedef void (CHAKRA_CALLBACK *JsHostPromiseRejectionTrackerCallback)(_In_ JsValueRef promise, _In_ JsValueRef reason, _In_ bool handled, _In_opt_ void *callbackState);
```
### Parameters
* __promise__: The promise object, represented as a JsValueRef.
* __reason__: The value/cause of the rejection, represented as a JsValueRef.
* __handled__: Boolean - false for promiseRejected: i.e. if the promise has just been rejected with no handler, true for promiseHandled: i.e. if it was rejected before without a handler and is now being handled.
* __callbackState__: The state passed to JsSetHostPromiseRejectionTracker.

### Remarks 
The host can specify a promise rejection tracker callback in <c>JsSetHostPromiseRejectionTracker</c>.
If a promise is rejected with no reactions or a reaction is added to a promise that was rejected
before it had reactions by default nothing is done.
A Promise Rejection Tracker callback may be set - which will then be called when this occurs.
Note - per ECMASpec #sec-host-promise-rejection-tracker this function should not set or return an exception.
Note also the promise and reason parameters may be garbage collected after this function is called if you wish to make further use of them you will need to use JsAddRef to preserve them.
However if you use JsAddRef you must also call JsRelease and not hold onto them after 
a handled notification (both per spec and to avoid memory leaks).