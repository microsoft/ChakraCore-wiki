Retrieves the data from an external object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetExternalData(
    _In_ JsValueRef object,
    _Out_ void **externalData);
```
### Parameters 
* __object__: The external object.
* __externalData__:  The external data stored in the object. Can be null if no external data is stored in the object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
