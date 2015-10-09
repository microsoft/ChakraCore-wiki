Gets a property descriptor for an object's own property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetOwnPropertyDescriptor(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _Out_ JsValueRef *propertyDescriptor);
```
### Parameters 
* __object__: The object that has the property.
* __propertyId__: The ID of the property.
* __propertyDescriptor__: The property descriptor.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
