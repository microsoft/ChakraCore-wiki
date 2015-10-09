A thread service callback.
### Syntax 
```
typedef bool (CALLBACK *JsThreadServiceCallback)(_In_ JsBackgroundWorkItemCallback callback, _In_opt_ void *callbackState);
```
### Parameters 
* __callback__: The callback for the background work item.
* __callbackState__: The data argument to be passed to the callback.

### Remarks 
The host can specify a background thread service when calling **JsCreateRuntime**. If specified, then background work items will be passed to the host using this callback. The host is expected to either begin executing the background work item immediately and return true or return false and the runtime will handle the work item in-thread.