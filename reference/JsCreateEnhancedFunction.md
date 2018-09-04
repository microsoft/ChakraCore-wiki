Creates a new enhanced JavaScript function.
### Syntax

```
CHAKRA_API
    JsCreateEnhancedFunction(
        _In_ JsEnhancedNativeFunction nativeFunction,
        _In_opt_ JsValueRef metadata,
        _In_opt_ void *callbackState,
        _Out_ JsValueRef *function);
```

### Parameters

* __nativeFunction__: The method to call when the function is invoked.
* __metadata__: If this is not **JS_INVALID_REFERENCE**, it is converted to a string and used as the name of the function.
* __callbackState__: User provided state that will be passed back to the callback.
* __function__: The new function object.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
