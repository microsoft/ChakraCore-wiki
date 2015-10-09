Creates a Javascript symbol. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateSymbol(
    _In_ JsValueRef description,
    _Out_ JsValueRef *result);
```
### Parameters 
* __description__: The string description of the symbol. Can be null.
* __result__: The new symbol.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
