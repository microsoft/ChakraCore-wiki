Performs a full garbage collection. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCollectGarbage(
    _In_ JsRuntimeHandle runtime);
```
### Parameters 
* __runtime__: The runtime in which the garbage collection will be performed.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
