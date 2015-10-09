A background work item callback.
### Syntax 
```
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(_In_opt_ void *callbackState);
```
### Parameters 
* __callbackState__: Data argument passed to the thread service.

### Remarks 
This is passed to the host's thread service (if provided) to allow the host to invoke the work item callback on the background thread of its choice.