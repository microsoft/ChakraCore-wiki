Gets a property descriptor for an object's own property.
### Syntax

```
CHAKRA_API
    JsObjectGetOwnPropertyDescriptor(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _Out_ JsValueRef *propertyDescriptor);
```

### Parameters

* __object__: The object that has the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __propertyDescriptor__: The property descriptor.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
