A callback called before collecting an object.
### Syntax 
```
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(_In_ JsRef ref, _In_opt_ void *callbackState);
```
### Parameters 
* __ref__: The object to be collected.
* __callbackState__: The state passed to <c>JsSetObjectBeforeCollectCallback

### Remarks
Use **JsSetObjectBeforeCollectCallback** to register this callback.