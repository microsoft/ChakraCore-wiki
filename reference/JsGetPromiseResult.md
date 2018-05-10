Gets the result of a given `Promise` object.

### Syntax 
```
CHAKRA_API
    JsGetPromiseResult(
        _In_ JsValueRef *promise,
        _Out_ JsValueRef *result);
```

### Parameters 
* __promise__: The `Promise` object.
* __result__: The result of the `Promise`. This contains the value passed to
  either the `resolve` or `reject` handler. Use `JsGetPromiseState` to determine
  whether the `Promise` was fulfilled or rejected.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise. If
the promise is still pending then `JsErrorPromisePending` will be returned.

### Remarks 
**This API is experimental and may have breaking change later.** 

Requires an active script context.