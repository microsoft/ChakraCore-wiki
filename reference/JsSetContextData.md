Sets the internal data of JsrtContext. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetContextData(
        _In_ JsContextRef context,
        _In_ void *data);
```
### Parameters 
* __context__: The context to set the data to.
* __data__: The pointer to the data to be set.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
