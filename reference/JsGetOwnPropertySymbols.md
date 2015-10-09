Gets the list of all symbol properties on the object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetOwnPropertySymbols(
    _In_ JsValueRef object,
    _Out_ JsValueRef *propertySymbols);
```
### Parameters 
* __object__: The object from which to get the property symbols.
* __propertySymbols__: An array of property symbols.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
