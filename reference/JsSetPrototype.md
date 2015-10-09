Sets the prototype of an object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetPrototype(
    _In_ JsValueRef object,
    _In_ JsValueRef prototypeObject);
```
### Parameters 
* __object__: The object whose prototype is to be changed.
* __prototypeObject__: The object's new prototype.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
