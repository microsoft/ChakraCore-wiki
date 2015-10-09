Sets an object's indexed properties to external data. The external data will be used as back store for the object's indexed properties and accessed like a typed array. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetIndexedPropertiesToExternalData(
    _In_ JsValueRef object,
    _In_ void* data,
    _In_ JsTypedArrayType arrayType,
    _In_ unsigned int elementLength);
```
### Parameters 
* __object__: The object to operate on.
* __data__: The external data to be used as back store for the object's indexed properties.
* __arrayType__: The array element type in external data.
* __elementLength__: The number of array elements in external data.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
