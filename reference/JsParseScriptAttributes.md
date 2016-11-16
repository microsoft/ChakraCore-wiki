Attribute mask for JsParseScriptWithAttributes
### Syntax 
```
enum JsParseScriptAttributes 
```
### Members 
* __JsParseScriptAttributeNone__: Default attribute
* __JsParseScriptAttributeLibraryCode__: Specified script is internal and non-user code. Hidden from debugger
* __JsParseScriptAttributeArrayBufferIsUtf16Encoded__: ChakraCore assumes ExternalArrayBuffer is Utf8 by default. This one needs to be set for Utf16
