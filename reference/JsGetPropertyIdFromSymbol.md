Gets the property ID associated with the symbol. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetPropertyIdFromSymbol(
    _In_ JsValueRef symbol,
    _Out_ JsPropertyIdRef *propertyId);
```
### Parameters 
* __symbol__:  The symbol whose property ID is being retrieved.
* __propertyId__: The property ID for the given symbol.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Property IDs are specific to a context and cannot be used across contexts.
Requires an active script context.
