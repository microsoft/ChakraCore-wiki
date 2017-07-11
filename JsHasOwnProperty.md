Determines whether an object has a non-inherited property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsHasOwnProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _Out_ bool *hasOwnProperty);
```
### Parameters 
* __object__: The object that may contain the property.
* __propertyId__: The ID of the property.
* __hasProperty__: Whether the object has the non-inherited property.
### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
