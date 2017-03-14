Parses a script and returns a function representing the script.

### Syntax
```
STDAPI_(JsErrorCode)
    JsParseScriptWithAttributes(
        _In_z_ const wchar_t *script,
        _In_ JsSourceContext sourceContext,
        _In_z_ const wchar_t *sourceUrl,
        _In_ JsParseScriptAttributes parseAttributes,
        _Out_ JsValueRef *result);
```

### Parameters
* __script__: The script to parse.
* __sourceContext__: A cookie identifying the script that can be used by debuggable script contexts.
* __sourceUrl__: The location the script came from.
* __parseAttributes__: Attribute mask for parsing the script
* __result__: A function representing the script code.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
This API is Windows-only.
