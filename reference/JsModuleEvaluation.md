Execute module code.
### Syntax 
```
CHAKRA_API
JsModuleEvaluation(
    _In_ JsModuleRecord requestModule,
    _Outptr_result_maybenull_ JsValueRef* result);
```
### Parameters 
* __requestModule__: The ModuleRecord being executed.
* __result__: The return value of the module.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
This method implements 15.2.1.1.6.5, "ModuleEvaluation" concrete method.
This method should be called after the engine notifies the host that the module is ready.
This method only needs to be called on root modules - it will execute all of the dependent modules.

One moduleRecord will be executed only once. Additional execution call on the same moduleRecord will fail.