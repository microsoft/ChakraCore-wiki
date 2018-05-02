Invokes a function. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCallFunction(
    _In_ JsValueRef function,
    _In_reads_(argumentCount) JsValueRef *arguments,
    _In_ unsigned short argumentCount,
    _Out_opt_ JsValueRef *result);
```
### Parameters 
* __function__: The function to invoke.
* __arguments__: A JsValueRef array of arguments to the call. `arguments[0]` is `thisArg` or `undefined` if the function is to be called plainly.
* __argumentCount__: The number of arguments being passed in to the function.
* __result__: The value returned from the function invocation, if any.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
Requires an active script context.