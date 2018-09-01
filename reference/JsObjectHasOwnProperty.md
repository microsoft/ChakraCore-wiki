Determines whether an object has a non-inherited property.
### Syntax

```
CHAKRA_API
    JsObjectHasOwnProperty(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _Out_ bool *hasOwnProperty);
```

### Parameters

* __object__: The object that may contain the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __hasOwnProperty__: Whether the object has the non-inherited property.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
