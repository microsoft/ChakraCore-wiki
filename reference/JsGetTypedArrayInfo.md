Obtains frequently used properties of a typed array. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetTypedArrayInfo(
    _In_ JsValueRef typedArray,
    _Out_opt_ JsTypedArrayType *arrayType,
    _Out_opt_ JsValueRef *arrayBuffer,
    _Out_opt_ unsigned int *byteOffset,
    _Out_opt_ unsigned int *byteLength);
```
### Parameters 
* __typedArray__: The typed array instance.
* __arrayType__: The type of the array.
* __arrayBuffer__: The ArrayBuffer backstore of the array.
* __byteOffset__: The offset in bytes from the start of arrayBuffer referenced by the array.
* __byteLength__: The number of bytes in the array.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
