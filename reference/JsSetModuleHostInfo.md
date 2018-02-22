Set host info for the specified module.
### Syntax 
```
CHAKRA_API
JsSetModuleHostInfo(
    _In_ JsModuleRecord requestModule,
    _In_ JsModuleHostInfoKind moduleHostInfo,
    _In_ void* hostInfo);
```
### Parameters 
* __requestModule__: The request module.
* __moduleHostInfo__: The type of host info to be set.
* __hostInfo__: The host info to be set.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
This is used for four things:
1. Setting up the callbacks for module loading - note these are actually set on the current Context not the module so only have to be set for the first root module in any given context.
2. Setting host defined info on a module record - can be anything that you wish to associate with your modules.
3. Setting a URL for a module to be used for stack traces/debugging - note this must be set before calling JsParseModuleSource on the module or it will be ignored.
4. Setting an exception on the module object - only relevant prior to it being Parsed.