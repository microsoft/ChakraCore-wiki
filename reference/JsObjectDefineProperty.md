Defines a new object's own property from a property descriptor.
### Syntax

```
CHAKRA_API
    JsObjectDefineProperty(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _In_ JsValueRef propertyDescriptor,
        _Out_ bool *result);
```

### Parameters

* __object__: The object that has the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __propertyDescriptor__: The property descriptor.
* __result__: Whether the property was defined.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
