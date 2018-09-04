Gets an object's property.
### Syntax

```
CHAKRA_API
    JsObjectGetProperty(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _Out_ JsValueRef *value);
```

### Parameters

* __object__: The object that contains the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __value__: The value of the property.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
