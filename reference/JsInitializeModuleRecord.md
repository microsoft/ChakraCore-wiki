Initialize a ModuleRecord from host.
### Syntax 
```
CHAKRA_API
JsInitializeModuleRecord(
    _In_opt_ JsModuleRecord referencingModule,
    _In_ JsValueRef normalizedSpecifier,
    _Outptr_result_maybenull_ JsModuleRecord* moduleRecord);
```
### Parameters 
* __referencingModule__: The parent module of the new module - nullptr for a root module.
* __normalizedSpecifier__: The normalized specifier for the module.
* __moduleRecord__: The new module record.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
**This API is experimental and may have breaking change later.**
Bootstrap the module loading process by creating a new module record.

