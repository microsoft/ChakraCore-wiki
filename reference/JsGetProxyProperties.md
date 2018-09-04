Determines if a provided object is a JavscriptProxy Object and provides references to a Proxy's target and handler.
### Syntax

```
CHAKRA_API
    JsGetProxyProperties(
        _In_ JsValueRef object,
        _Out_ bool* isProxy,
        _Out_opt_ JsValueRef* target,
        _Out_opt_ JsValueRef* handler);
```

### Parameters

* __object__: The object that may be a Proxy.
* __isProxy__: Pointer to a Boolean - is the object a proxy?
* __target__: Pointer to a JsValueRef - the object's target.
* __handler__: Pointer to a JsValueRef - the object's handler.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context. If object is not a Proxy object the target and handler parameters are not touched. If nullptr is supplied for target or handler the function returns after setting the isProxy value. If the object is a revoked Proxy target and handler are set to JS_INVALID_REFERENCE. If it is a Proxy object that has not been revoked target and handler are set to the the object's target and handler.
