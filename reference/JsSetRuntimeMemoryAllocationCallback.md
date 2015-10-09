Sets a memory allocation callback for specified runtime 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetRuntimeMemoryAllocationCallback(
    _In_ JsRuntimeHandle runtime,
    _In_opt_ void *callbackState,
    _In_ JsMemoryAllocationCallback allocationCallback);
```
### Parameters 
* __runtime__: The runtime for which to register the allocation callback.
* __callbackState__:  User provided state that will be passed back to the callback.
* __allocationCallback__:  Memory allocation callback to be called for memory allocation events.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Registering a memory allocation callback will cause the runtime to call back to the host
whenever it acquires memory from, or releases memory to, the OS. The callback routine is
called before the runtime memory manager allocates a block of memory. The allocation will
be rejected if the callback returns false. The runtime memory manager will also invoke the
callback routine after freeing a block of memory, as well as after allocation failures.
The callback is invoked on the current runtime execution thread, therefore execution is
blocked until the callback completes.
The return value of the callback is not stored; previously rejected allocations will not
prevent the runtime from invoking the callback again later for new memory allocations.
