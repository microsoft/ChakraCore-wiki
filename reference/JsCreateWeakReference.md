Creates a weak reference to a value.
### Syntax 
```
CHAKRA_API
    JsCreateWeakReference(
        _In_ JsValueRef value,
        _Out_ JsWeakRef* weakRef);
```
### Parameters 
* __value__:  The value to be referenced.
* __weakRef.__: Weak reference to the value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking change later.**
