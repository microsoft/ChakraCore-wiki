Retrieve the host info for the specified module.
### Syntax 
```
CHAKRA_API
JsGetModuleHostInfo(
    _In_ JsModuleRecord requestModule,
    _In_ JsModuleHostInfoKind moduleHostInfo,
    _Outptr_result_maybenull_ void** hostInfo);
```
### Parameters 
* __requestModule__: The request module.
* __moduleHostInfo__: The type of host info to be retrieved.
* __hostInfo__: The retrieved host info for the module.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
This can used to retrieve info previously set with JsSetModuleHostInfo.