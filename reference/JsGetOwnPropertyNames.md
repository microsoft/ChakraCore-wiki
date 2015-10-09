Gets the list of all properties on the object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetOwnPropertyNames(
    _In_ JsValueRef object,
    _Out_ JsValueRef *propertyNames);
```
### Parameters 
* __object__: The object from which to get the property names.
* __propertyNames__: An array of property names.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
