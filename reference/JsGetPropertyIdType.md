opertyIdTypeSymbol ertyIdType; Gets the type of property 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetPropertyIdType(
    _In_ JsPropertyIdRef propertyId,
    _Out_ JsPropertyIdType* propertyIdType);
```
### Parameters 
* __propertyId__: The property ID to get the type of.
* __propertyIdType__: The JsPropertyIdType of the given property ID

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
