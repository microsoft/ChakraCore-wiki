Creates the property ID associated with the name.
### Syntax 
```
CHAKRA_API
       JsCreatePropertyIdUtf8(
        _In_z_ const char *name,
        _In_ size_t length,
        _Out_ JsPropertyIdRef *propertyId);
```
### Parameters 
* __name__: The name of the property ID to get or create. The name may consist of only digits. The string is expected to be ASCII / utf8 encoded.
* __length__: Length of the name in bytes
* __propertyId__: The property ID in this runtime for the given name


### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.

Property IDs are specific to a context and cannot be used across contexts.
