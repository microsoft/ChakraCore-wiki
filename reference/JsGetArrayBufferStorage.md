Obtains the underlying memory storage used by an **ArrayBuffer**. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetArrayBufferStorage(
    _In_ JsValueRef arrayBuffer,
    _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,
    _Out_ unsigned int *bufferLength);
```
### Parameters 
* __arrayBuffer__: The ArrayBuffer instance.
* __buffer__:  The ArrayBuffer's buffer. The lifetime of the buffer returned is the same as the lifetime of the the ArrayBuffer. The buffer pointer does not count as a reference to the ArrayBuffer for the purpose of garbage collection.
* __bufferLength__: The number of bytes in the buffer.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
