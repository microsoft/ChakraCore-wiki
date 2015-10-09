Gets the symbol associated with the property ID. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetSymbolFromPropertyId(
    _In_ JsPropertyIdRef propertyId,
    _Out_ JsValueRef *symbol);
```
### Parameters 
* __propertyId__: The property ID to get the symbol of.
* __symbol__: The symbol associated with the property ID.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
