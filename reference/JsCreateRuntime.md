Creates a new runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateRuntime(
    _In_ JsRuntimeAttributes attributes,
    _In_opt_ JsThreadServiceCallback threadService,
    _Out_ JsRuntimeHandle *runtime);
```
### Parameters 
* __attributes__: The attributes of the runtime to be created.
* __threadService__: The thread service for the runtime. Can be null.
* __runtime__: The runtime created.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
