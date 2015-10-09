Sets the current memory limit for a runtime. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetRuntimeMemoryLimit(
    _In_ JsRuntimeHandle runtime,
    _In_ size_t memoryLimit);
```
### Parameters 
* __runtime__: The runtime whose memory limit is to be set.
* __memoryLimit__:  The new runtime memory limit, in bytes, or -1 for no memory limit.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
A memory limit will cause any operation which exceeds the limit to fail with an "out of
memory" error. Setting a runtime's memory limit to -1 means that the runtime has no memory
limit. New runtimes  default to having no memory limit. If the new memory limit exceeds
current usage, the call will succeed and any future allocations in this runtime will fail
until the runtime's memory usage drops below the limit.
A runtime's memory limit can be always be set, regardless of whether or not the runtime is
active on another thread.
