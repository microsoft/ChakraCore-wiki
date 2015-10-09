Puts an object's property. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetProperty(
    _In_ JsValueRef object,
    _In_ JsPropertyIdRef propertyId,
    _In_ JsValueRef value,
    _In_ bool useStrictRules);
```
### Parameters 
* __object__: The object that contains the property.
* __propertyId__: The ID of the property.
* __value__: The new value of the property.
* __useStrictRules__: The property set should follow strict mode rules.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
