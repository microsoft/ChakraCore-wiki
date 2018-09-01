Decrease the reference count on a SharedArrayBuffer storage object.
### Syntax

```
CHAKRA_API
    JsReleaseSharedArrayBufferContentHandle(
        _In_ JsSharedArrayBufferContentHandle sharedContents);
```

### Parameters

* __sharedContents__: The storage object of a SharedArrayBuffer which can be shared between multiple thread.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
