Creates a new object that stores some external data. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateExternalObject(
    _In_opt_ void *data,
    _In_opt_ JsFinalizeCallback finalizeCallback,
    _Out_ JsValueRef *object);
```
### Parameters 
* __data__: External data that the object will represent. May be null.
* __finalizeCallback__:  A callback for when the object is finalized. May be null.
* __object__: The new object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
