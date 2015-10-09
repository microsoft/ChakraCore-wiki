Sets the external data on an external object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetExternalData(
    _In_ JsValueRef object,
    _In_opt_ void *externalData);
```
### Parameters 
* __object__: The external object.
* __externalData__:  The external data to be stored in the object. Can be null if no external data is to be stored in the object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
