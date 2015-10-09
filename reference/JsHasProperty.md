Determines whether an object has a property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _Out_ bool *hasProperty);
```
### Parameters 
* __object__: The object that may contain the property.
* __propertyId__: The ID of the property.
* __hasProperty__: Whether the object (or a prototype) has the property.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
