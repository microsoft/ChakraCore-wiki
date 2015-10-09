Gets the internal data set on JsrtContext. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetContextData(
        _In_ JsContextRef context,
        _Out_ void **data);
```
### Parameters 
* __context__: The context to get the data from.
* __data__: The pointer to the data where data will be returned.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
