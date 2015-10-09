Gets the current memory limit for a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetRuntimeMemoryLimit(
    _In_ JsRuntimeHandle runtime,
    _Out_ size_t *memoryLimit);
```
### Parameters 
* __runtime__: The runtime whose memory limit is to be retrieved.
* __memoryLimit__:  The runtime's current memory limit, in bytes, or -1 if no limit has been set.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
The memory limit of a runtime can be always be retrieved, regardless of whether or not the
runtime is active on another thread.
