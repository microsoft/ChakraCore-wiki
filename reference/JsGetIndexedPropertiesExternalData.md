Retrieves an object's indexed properties external data information. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetIndexedPropertiesExternalData(
    _In_ JsValueRef object,
    _Out_ void** data,
    _Out_ JsTypedArrayType* arrayType,
    _Out_ unsigned int* elementLength);
```
### Parameters 
* __object__: The object.
* __data__: The external data back store for the object's indexed properties.
* __arrayType__: The array element type in external data.
* __elementLength__: The number of array elements in external data.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
