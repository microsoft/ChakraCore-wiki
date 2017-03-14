Executes a script. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsRunScript(
    _In_z_ const wchar_t *script,
    _In_ JsSourceContext sourceContext,
    _In_z_ const wchar_t *sourceUrl,
    _Out_ JsValueRef *result);
```
### Parameters 
* __script__: The script to run.
* __sourceContext__:  A cookie identifying the script that can be used by debuggable script contexts.
* __sourceUrl__: The location the script came from.
* __result__: The result of the script, if any. This parameter can be null.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
This API is Windows-only (see [[JsRun]] for cross-platform equivalent).
Requires an active script context.
