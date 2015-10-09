Disposes a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDisposeRuntime(
    _In_ JsRuntimeHandle runtime);
```
### Parameters 
* __runtime__: The runtime to dispose.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Once a runtime has been disposed, all resources owned by it are invalid and cannot be used.
If the runtime is active (i.e. it is set to be current on a particular thread), it cannot
be disposed.
