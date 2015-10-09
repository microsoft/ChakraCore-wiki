Makes an object non-extensible. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsPreventExtension(
    _In_ JsValueRef object);
```
### Parameters 
* __object__: The object to make non-extensible.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
