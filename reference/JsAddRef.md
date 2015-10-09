Adds a reference to a garbage collected object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsAddRef(
    _In_ JsRef ref,
    _Out_opt_ unsigned int *count);
```
### Parameters 
* __ref__: The object to add a reference to.
* __count__: The object's new reference count (can pass in null).

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
This only needs to be called on **JsRef** handles that are not going to be stored
somewhere on the stack. Calling **JsAddRef** ensures that the object the **JsRef**
refers to will not be freed until **JsRelease** is called.
