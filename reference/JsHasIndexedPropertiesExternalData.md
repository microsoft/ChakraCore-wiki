Determines whether an object has its indexed properties in external data. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasIndexedPropertiesExternalData(
    _In_ JsValueRef object,
    _Out_ bool* value);
```
### Parameters 
* __object__: The object.
* __value__: Whether the object has its indexed properties in external data.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
