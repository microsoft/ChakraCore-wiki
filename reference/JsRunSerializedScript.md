Runs a serialized script. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsRunSerializedScript(
    _In_z_ const wchar_t *script,
    _In_ BYTE *buffer,
    _In_ JsSourceContext sourceContext,
    _In_z_ const wchar_t *sourceUrl,
    _Out_ JsValueRef *result);
```
### Parameters 
* __script__: The source code of the serialized script.
* __buffer__: The serialized script.
* __sourceContext__:  A cookie identifying the script that can be used by debuggable script contexts.
* __sourceUrl__: The location the script came from.
* __result__:  The result of running the script, if any. This parameter can be null.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
The runtime will hold on to the buffer until all instances of any functions created from
the buffer are garbage collected.
