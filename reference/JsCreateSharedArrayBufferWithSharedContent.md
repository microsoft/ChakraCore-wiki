Creates a Javascript SharedArrayBuffer object with shared content get from JsGetSharedArrayBufferContent.
### Syntax

```
CHAKRA_API
    JsCreateSharedArrayBufferWithSharedContent(
        _In_ JsSharedArrayBufferContentHandle sharedContents,
        _Out_ JsValueRef *result);
```

### Parameters

* __sharedContents__: The storage object of a SharedArrayBuffer which can be shared between multiple thread.
* __result__: The new SharedArrayBuffer object.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
