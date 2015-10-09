Releases a reference to a garbage collected object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsRelease(
    _In_ JsRef ref,
    _Out_opt_ unsigned int *count);
```
### Parameters 
* __ref__: The object to add a reference to.
* __count__: The object's new reference count (can pass in null).

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Removes a reference to a **JsRef** handle that was created by **JsAddRef**.
