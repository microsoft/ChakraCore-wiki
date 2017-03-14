Serializes a parsed script to a buffer than can be reused. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSerializeScript(
    _In_z_ const wchar_t *script,
    _Out_writes_to_opt_(*bufferSize, *bufferSize) BYTE *buffer,
    _Inout_ unsigned long *bufferSize);
```
### Parameters 
* __script__: The script to serialize.
* __buffer__: The buffer to put the serialized script into. Can be null.
* __bufferSize__:  On entry, the size of the buffer, in bytes; on exit, the size of the buffer, in bytes, required to hold the serialized script.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
This API is Windows-only.
**JsSerializeScript** parses a script and then stores the parsed form of the script in a
runtime-independent format. The serialized script then can be deserialized in any
runtime without requiring the script to be re-parsed.
Requires an active script context.
