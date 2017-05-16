Gets a strong reference to the value referred to by a weak reference.
### Syntax 
```
CHAKRA_API
    JsGetWeakReferenceValue(
        _In_ JsWeakRef weakRef,
        _Out_ JsValueRef* value);
```
### Parameters
* __value__:  Reference to the value, or __JS_INVALID_REFERENCE__ if the value is no longer available.
* __weakRef__: A weak reference.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking change later.**
