A weak reference to a JavaScript value.

### Syntax 
```
typedef JsRef JsWeakRef;
```
### Remarks
**This API is experimental and may have breaking change later.** 

A value with only weak references is available for garbage-collection. A strong reference
to the value (__JsValueRef__) may be obtained from a weak reference if the value happens
to still be available.