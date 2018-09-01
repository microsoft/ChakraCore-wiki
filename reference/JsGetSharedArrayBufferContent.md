Get the storage object from a SharedArrayBuffer.
### Syntax

```
CHAKRA_API
    JsGetSharedArrayBufferContent(
        _In_ JsValueRef sharedArrayBuffer,
        _Out_ JsSharedArrayBufferContentHandle *sharedContents);
```

### Parameters

* __sharedArrayBuffer__: The SharedArrayBuffer object.
* __sharedContents__: The storage object of a SharedArrayBuffer which can be shared between multiple thread. User should call JsReleaseSharedArrayBufferContentHandle after finished using it.

### Return Value
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks
**This API is experimental and may have breaking changes later.**

Requires an active script context.
