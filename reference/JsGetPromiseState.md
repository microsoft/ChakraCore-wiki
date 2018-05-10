Gets the state of a given `Promise` object.

### Syntax 
```
CHAKRA_API
    JsGetPromiseState(
        _In_ JsValueRef *promise,
        _Out_ JsPromiseState *state);
```

### Parameters 
* __promise__: The `Promise` object.
* __state__: The current state of the `Promise` object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.** 

Requires an active script context.