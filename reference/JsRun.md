Executes a script.
### Syntax 
```
CHAKRA_API
    JsRun(
        _In_ JsValueRef script,
        _In_ JsSourceContext sourceContext,
        _In_ JsValueRef sourceUrl,
        _In_ JsParseScriptAttributes parseAttributes,
        _Out_ JsValueRef *result);
```
### Parameters 
* __script__: The script to run.
* __sourceContext__: A cookie identifying the script that can be used by debuggable script contexts.
* __sourceUrl__: The location the script came from
* __parseAttributes__: Attribute mask for parsing the script
* __result__: The result of the script, if any. This parameter can be null.


### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.

Script source can be either JavascriptString or JavascriptExternalArrayBuffer.
In case it is an ExternalArrayBuffer, and the encoding of the buffer is Utf16,
JsParseScriptAttributeArrayBufferIsUtf16Encoded is expected on parseAttributes.

Use JavascriptExternalArrayBuffer with Utf8/ASCII script source
for better performance and smaller memory footprint.