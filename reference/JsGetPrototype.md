Returns the prototype of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetPrototype(
    _In_ JsValueRef object,
    _Out_ JsValueRef *prototypeObject);
```
### Parameters 
* __object__: The object whose prototype is to be returned.
* __prototypeObject__: The object's prototype.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
