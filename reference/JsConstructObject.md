Invokes a function as a constructor. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsConstructObject(
    _In_ JsValueRef function,
    _In_reads_(argumentCount) JsValueRef *arguments,
    _In_ unsigned short argumentCount,
    _Out_ JsValueRef *result);
```
### Parameters 
* __function__: The function to invoke as a constructor.
* __arguments__: The arguments to the call.
* __argumentCount__: The number of arguments being passed in to the function.
* __result__: The value returned from the function invocation.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
