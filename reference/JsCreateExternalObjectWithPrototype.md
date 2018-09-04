Creates a new object (with prototype) that stores some external data.
### Syntax

```
CHAKRA_API
    JsCreateExternalObjectWithPrototype(
        _In_opt_ void *data,
        _In_opt_ JsFinalizeCallback finalizeCallback,
        _In_opt_ JsValueRef prototype,
        _Out_ JsValueRef *object);
```

### Parameters

* __data__: External data that the object will represent. May be null.
* __finalizeCallback__: A callback for when the object is finalized. May be null.
* __prototype__: Prototype object or nullptr.
* __object__: The new object.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
