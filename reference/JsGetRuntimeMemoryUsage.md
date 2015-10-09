Gets the current memory usage for a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetRuntimeMemoryUsage(
    _In_ JsRuntimeHandle runtime,
    _Out_ size_t *memoryUsage);
```
### Parameters 
* __runtime__: The runtime whose memory usage is to be retrieved.
* __memoryUsage__: The runtime's current memory usage, in bytes.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Memory usage can be always be retrieved, regardless of whether or not the runtime is active
on another thread.
