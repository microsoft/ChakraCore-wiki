Creates a Javascript ArrayBuffer object to access external memory. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateExternalArrayBuffer(
    _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,
    _In_ unsigned int byteLength,
    _In_opt_ JsFinalizeCallback finalizeCallback,
    _In_opt_ void *callbackState,
    _Out_ JsValueRef *result);
```
### Parameters 
* __data__: A pointer to the external memory.
* __byteLength__: The number of bytes in the external memory.
* __finalizeCallback__: A callback for when the object is finalized. May be null.
* __callbackState__: User provided state that will be passed back to finalizeCallback.
* __result__: The new ArrayBuffer object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
