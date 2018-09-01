Deletes an object's property.
### Syntax

```
CHAKRA_API
    JsObjectDeleteProperty(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _In_ bool useStrictRules,
        _Out_ JsValueRef *result);
```

### Parameters

* __object__: The object that contains the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __useStrictRules__: The property set should follow strict mode rules.
* __result__: Whether the property was deleted.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
