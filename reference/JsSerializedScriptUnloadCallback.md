Called by the runtime when it is finished with all resources related to the script execution. The caller should free the source if loaded, the byte code, and the context at this time.
### Syntax 
```
typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(_In_ JsSourceContext sourceContext);
```
### Parameters 
* __sourceContext__: The context passed to Js[Parse|Run]SerializedScriptWithCallback
