Creates a Javascript DataView object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateDataView(
    _In_ JsValueRef arrayBuffer,
    _In_ unsigned int byteOffset,
    _In_ unsigned int byteLength,
    _Out_ JsValueRef *result);
```
### Parameters 
* __arrayBuffer__:  An existing ArrayBuffer object to use as the storage for the result DataView object.
* __byteOffset__:  The offset in bytes from the start of arrayBuffer for result DataView to reference.
* __byteLength__:  The number of bytes in the ArrayBuffer for result DataView to reference.
* __result__: The new DataView object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
