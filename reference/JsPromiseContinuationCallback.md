A promise continuation callback.
### Syntax 
```
typedef void (CALLBACK *JsPromiseContinuationCallback)(_In_ JsValueRef task, _In_opt_ void *callbackState);
```
### Parameters 
* __task__: The task, represented as a JavaScript function.
* __callbackState__: The data argument to be passed to the callback.

### Remarks
The host can specify a promise continuation callback in **JsSetPromiseContinuationCallback**. If a script creates a task to be run later, then the promise continuation callback will be called with the task and the task should be put in a FIFO queue, to be run when the current script is done executing.