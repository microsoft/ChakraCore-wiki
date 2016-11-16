Runs a serialized script.
Provides the ability to lazy load the script source only if/when it is needed.

### Syntax 
```
CHAKRA_API
       JsRunSerialized(
        _In_ BYTE *buffer,
        _In_ JsSerializedLoadScriptCallback scriptLoadCallback,
        _In_ JsSourceContext sourceContext,
        _In_ JsValueRef sourceUrl,
        _Out_ JsValueRef *result);
```
### Parameters 
* __buffer__: The serialized script
* __scriptLoadCallback__: Callback called when the source code of the script needs to be loaded
* __sourceContext__: A cookie identifying the script that can be used by debuggable script contexts. This context will passed into scriptLoadCallback.
* __sourceUrl__: The location the script came from.
* __result__: The result of running the script, if any. This parameter can be null.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.

The runtime will hold on to the buffer until all instances of any functions created from the buffer are garbage collected.