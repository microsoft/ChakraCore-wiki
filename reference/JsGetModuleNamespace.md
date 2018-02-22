Retrieve the namespace object for a module.
### Syntax 
```
JsGetModuleNamespace(
        _In_ JsModuleRecord requestModule,
        _Outptr_result_maybenull_ JsValueRef *moduleNamespace);
```
### Parameters 
* __requestModule__: The JsModuleRecord for which the namespace is being requested.
* __moduleNamespace__: A JsValueRef - the requested namespace object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
Requires an active script context and that the module has already been evaluated.