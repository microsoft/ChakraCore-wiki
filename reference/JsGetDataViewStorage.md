Obtains the underlying memory storage used by a DataView. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetDataViewStorage(
    _In_ JsValueRef dataView,
    _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,
    _Out_ unsigned int *bufferLength);
```
### Parameters 
* __dataView__: The DataView instance.
* __buffer__:  The DataView's buffer. The lifetime of the buffer returned is the same as the lifetime of the the DataView. The buffer pointer does not count as a reference to the DataView for the purpose of garbage collection.
* __bufferLength__: The number of bytes in the buffer.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
