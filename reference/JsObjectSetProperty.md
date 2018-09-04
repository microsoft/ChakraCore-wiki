Puts an object's property.
### Syntax

```
CHAKRA_API
    JsObjectSetProperty(
        _In_ JsValueRef object,
        _In_ JsValueRef key,
        _In_ JsValueRef value,
        _In_ bool useStrictRules);
```

### Parameters

* __object__: The object that contains the property.
* __key__: The key (JavascriptString or JavascriptSymbol) to the property.
* __value__: The new value of the property.
* __useStrictRules__: The property set should follow strict mode rules.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
