Parses a script and stores the generated parser state cache into a buffer which can be reused.
### Syntax

```
CHAKRA_API
    JsSerializeParserState(
        _In_ JsValueRef scriptVal,
        _Out_ JsValueRef *bufferVal,
        _In_ JsParseScriptAttributes parseAttributes);
```

### Parameters

* __scriptVal__: The script to parse.
* __bufferVal__: The buffer to put the serialized parser state cache into.
* __parseAttributes__: Encoding for the script.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

**JsSerializeParserState** parses a script and then stores a cache of the parser state in a runtime-independent format. The parser state may be deserialized in any runtime along with the same script to skip the initial parse phase.
 Requires an active script context.
 Script source can be either JavascriptString or JavascriptExternalArrayBuffer. In case it is an ExternalArrayBuffer, and the encoding of the buffer is Utf16, JsParseScriptAttributeArrayBufferIsUtf16Encoded is expected on parseAttributes.
 Use JavascriptExternalArrayBuffer with Utf8/ASCII script source for better performance and smaller memory footprint.
