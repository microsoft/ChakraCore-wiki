Defines a new object's own property from a property descriptor. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDefineProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _In_ JsValueRef propertyDescriptor,
    _Out_ bool *result);
```
### Parameters 
* __object__: The object that has the property.
* __propertyId__: The ID of the property.
* __propertyDescriptor__: The property descriptor.
* __result__: Whether the property was defined.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
