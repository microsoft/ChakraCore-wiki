Tells the runtime to do any idle processing it need to do. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsIdle(
    _Out_opt_ unsigned int *nextIdleTick);
```
### Parameters 
* __nextIdleTick__:  The next system tick when there will be more idle work to do. Can be null. Returns the maximum number of ticks if there no upcoming idle work to do.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
If idle processing has been enabled for the current runtime, calling **JsIdle** will
inform the current runtime that the host is idle and that the runtime can perform
memory cleanup tasks.
**JsIdle** can also return the number of system ticks until there will be more idle work
for the runtime to do. Calling **JsIdle** before this number of ticks has passed will do
no work.
Requires an active script context.
