Obtains the underlying memory storage used by a typed array. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetTypedArrayStorage(
    _In_ JsValueRef typedArray,
    _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,
    _Out_ unsigned int *bufferLength,
    _Out_opt_ JsTypedArrayType *arrayType,
    _Out_opt_ int *elementSize);
```
### Parameters 
* __typedArray__: The typed array instance.
* __buffer__:  The array's buffer. The lifetime of the buffer returned is the same as the lifetime of the the array. The buffer pointer does not count as a reference to the array for the purpose of garbage collection.
* __bufferLength__: The number of bytes in the buffer.
* __arrayType__: The type of the array.
* __elementSize__:  The size of an element of the array.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
