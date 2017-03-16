Parses a serialized script and returns a function representing the script.
Provides the ability to lazy load the script source only if/when it is needed.

### Syntax 
```
CHAKRA_API
       JsParseSerialized(
        _In_ BYTE *buffer,
        _In_ JsSerializedLoadScriptCallback scriptLoadCallback,
        _In_ JsSourceContext sourceContext,
        _In_ JsValueRef sourceUrl,
        _Out_ JsValueRef *result);
```
### Parameters 
* __buffer__: The serialized script
* __scriptLoadCallback__: Callback called when the source code of the script needs to be loaded. This is an optional parameter, set to null if not needed.
* __sourceContext__: A cookie identifying the script that can be used by debuggable script contexts. This context will passed into scriptLoadCallback.
* __sourceUrl__: The location the script came from.
* __result__: A function representing the script code.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking change later.**

Requires an active script context.