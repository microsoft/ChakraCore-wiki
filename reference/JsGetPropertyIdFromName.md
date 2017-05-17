Gets the property ID associated with the name. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetPropertyIdFromName(
    _In_z_ const wchar_t *name,
    _Out_ JsPropertyIdRef *propertyId);
```
### Parameters
* __name__:  The name of the property ID to get or create. The name may consist of only digits.
* __propertyId__: The property ID in this runtime for the given name.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
This API is Windows-only (see [[JsCreatePropertyIdUtf8]] for cross-platform equivalent).
Property IDs are specific to a context and cannot be used across contexts.
Requires an active script context.
