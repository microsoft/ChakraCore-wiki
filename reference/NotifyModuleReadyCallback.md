User implemented callback to get notification when the module is ready.
### Syntax 
```
typedef JsErrorCode (CHAKRA_CALLBACK * NotifyModuleReadyCallback) (
    _In_opt_ JsModuleRecord referencingModule,
    _In_opt_ JsValueRef exceptionVar);
```
### Parameters 
* __referencingModule__: The referencing module that has finished running ModuleDeclarationInstantiation step.
* __exceptionVar__:  If nullptr, the module is successfully initialized and host should queue the execution job otherwise it's the exception object.

### Return Value 
Returns a JsErrorCode - note, the return value is ignored.

### Remarks 
The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes. This callback should schedule a call to JsEvaluateModule to run the module that has been loaded.
