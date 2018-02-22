The types of host info that can be set on a module record with JsSetModuleHostInfo.
### Syntax 
```
enum JsModuleHostInfoKind
```
### Members 
* __JsModuleHostInfo_Exception__: An exception object - e.g. if the module file cannot be found.
* __JsModuleHostInfo_HostDefined__: Host defined info.
* __JsModuleHostInfo_NotifyModuleReadyCallback__: Callback for receiving notification when module is ready.
* __JsModuleHostInfo_FetchImportedModuleCallback__: Callback for receiving notification to fetch a dependent module.
* __JsModuleHostInfo_FetchImportedModuleFromScriptCallback__: Callback for receiving notification for calls to ```import()```
* __JsModuleHostInfo_Url__: URL for use in error stack traces and debugging.

### Remarks
For more information see JsSetModuleHostInfo.
