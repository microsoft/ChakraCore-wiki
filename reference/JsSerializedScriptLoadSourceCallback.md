Called by the runtime to load the source code of the serialized script. The caller must keep the script buffer valid until the JsSerializedScriptUnloadCallback.
### Syntax 
```
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(_In_ JsSourceContext sourceContext, _Outptr_result_z_ const wchar_t** scriptBuffer);
```
### Parameters 
* __sourceContext__: The context passed to Js[Parse|Run]SerializedScriptWithCallback
* __scriptBuffer__: The script returned.

### Return Value 
true if the operation succeeded, false otherwise.
