Creates a new object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateObject(
    _Out_ JsValueRef *object);
```
### Parameters 
* __object__: The new object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
