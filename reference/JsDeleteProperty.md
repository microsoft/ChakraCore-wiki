Deletes an object's property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsDeleteProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _In_ bool useStrictRules,
    _Out_ JsValueRef *result);
```
### Parameters 
* __object__: The object that contains the property.
* __propertyId__: The ID of the property.
* __useStrictRules__: The property set should follow strict mode rules.
* __result__: Whether the property was deleted.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
