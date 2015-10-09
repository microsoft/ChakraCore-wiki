User implemented callback routine for memory allocation events
### Syntax 
```
typedef bool (CALLBACK * JsMemoryAllocationCallback)(_In_opt_ void *callbackState, _In_ JsMemoryEventType allocationEvent, _In_ size_t allocationSize);
```
### Parameters 
* __callbackState__: The state passed to **JsSetRuntimeMemoryAllocationCallback**
* __allocationEvent__: The type of type allocation event.
* __allocationSize__: The size of the allocation.

### Return Value 
For the **JsMemoryAllocate** event, returning **true** allows the runtime to continue with the allocation. Returning false indicates the allocation request is rejected. The return value is ignored for other allocation events.
### Remarks 
Use **JsSetRuntimeMemoryAllocationCallback** to register this callback.