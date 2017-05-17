Called by the runtime to load the source code of the serialized script.
### Syntax 
```
typedef bool (CHAKRA_CALLBACK * JsSerializedLoadScriptCallback) (JsSourceContext sourceContext, _Out_ JsValueRef *value, _Out_ JsParseScriptAttributes *parseAttributes);
```
### Parameters 
* __sourceContext__: The context passed to Js[Parse|Run]SerializedScriptCallback
* __value__:  The script returned.
* __parseAttributes__: Parse Attributes returned

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.** The callback is invoked on the current runtime execution thread, therefore execution is
blocked until the callback completes.
The callback can be used by hosts to prepare for garbage collection. For example, by
releasing unnecessary references on Chakra objects.