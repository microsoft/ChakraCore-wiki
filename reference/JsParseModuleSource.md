Parse the source for an ES module
### Syntax 
```
CHAKRA_API
JsParseModuleSource(
    _In_ JsModuleRecord requestModule,
    _In_ JsSourceContext sourceContext,
    _In_ BYTE* script,
    _In_ unsigned int scriptLength,
    _In_ JsParseModuleSourceFlags sourceFlag,
    _Outptr_result_maybenull_ JsValueRef* exceptionValueRef);
```
### Parameters 
* __requestModule__: The ModuleRecord being parsed.
* __sourceContext__: A cookie identifying the script that can be used by debuggable script contexts.
* __script__: The source script to be parsed, but not executed in this code.
* __scriptLength__: The length of sourceText in bytes. As the input might contain a embedded null.
* __sourceFlag__: The type of the source code passed in. It could be utf16 or utf8 at this time.
* __exceptionValueRef__: The error object if there is a ParseError.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
This is basically ParseModule operation in ES6 spec. It is slightly different in that:
a) The ModuleRecord was initialized earlier, and passed in as an argument.
b) This includes a check to see if the module being Parsed is the last module in the dependency tree. If it is it automatically triggers Module Instantiation.