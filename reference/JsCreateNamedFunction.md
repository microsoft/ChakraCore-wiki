Creates a new JavaScript function with name. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateNamedFunction(
    _In_ JsValueRef name,
    _In_ JsNativeFunction nativeFunction,
    _In_opt_ void *callbackState,
    _Out_ JsValueRef *function);
```
### Parameters 
* __name__: The name of this function that will be used for diagnostics and stringification purposes.
* __nativeFunction__: The method to call when the function is invoked.
* __callbackState__:  User provided state that will be passed back to the callback.
* __function__: The new function object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
