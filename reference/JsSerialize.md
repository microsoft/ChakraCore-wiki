Serializes a parsed script to a buffer than can be reused.
### Syntax 
```
CHAKRA_API
       JsSerialize(
        _In_ JsValueRef script,
        _Out_ JsValueRef *buffer,
        _In_ JsParseScriptAttributes parseAttributes);
```
### Parameters 
* __script__: The script to serialize
* __buffer__: ArrayBuffer
* __parseAttributes__: Encoding for the script

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**

`JsSerializeScript` parses a script and then stores the parsed form of the script in a
runtime-independent format. The serialized script then can be deserialized in any
runtime without requiring the script to be re-parsed.

Script source can be either JavascriptString or JavascriptExternalArrayBuffer.
In case it is an ExternalArrayBuffer, and the encoding of the buffer is Utf16,
JsParseScriptAttributeArrayBufferIsUtf16Encoded is expected on parseAttributes.

Requires an active script context.

Use JavascriptExternalArrayBuffer with Utf8/ASCII script source
for better performance and smaller memory footprint.