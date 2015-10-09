Creates a Javascript ArrayBuffer object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateArrayBuffer(
    _In_ unsigned int byteLength,
    _Out_ JsValueRef *result);
```
### Parameters 
* __byteLength__:  The number of bytes in the ArrayBuffer.
* __result__: The new ArrayBuffer object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
