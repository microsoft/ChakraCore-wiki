Gets an object's property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _Out_ JsValueRef *value);
```
### Parameters 
* __object__: The object that contains the property.
* __propertyId__: The ID of the property.
* __value__: The value of the property.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
