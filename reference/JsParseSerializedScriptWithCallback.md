Parses a serialized script and returns a function representing the script. Provides the ability to lazy load the script source only if/when it is needed. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsParseSerializedScriptWithCallback(
    _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,
    _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,
    _In_ BYTE *buffer,
    _In_ JsSourceContext sourceContext,
    _In_z_ const wchar_t *sourceUrl,
    _Out_ JsValueRef * result);
```
### Parameters 
* __scriptLoadCallback__: Callback called when the source code of the script needs to be loaded.
* __scriptUnloadCallback__: Callback called when the serialized script and source code are no longer needed.
* __buffer__: The serialized script.
* __sourceContext__:  A cookie identifying the script that can be used by debuggable script contexts. This context will passed into scriptLoadCallback and scriptUnloadCallback.
* __sourceUrl__: The location the script came from.
* __result__: A function representing the script code.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
The runtime will hold on to the buffer until all instances of any functions created from
the buffer are garbage collected.  It will then call scriptUnloadCallback to inform the
caller it is safe to release.
