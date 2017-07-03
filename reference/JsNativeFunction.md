A function callback.
### Syntax 
```
typedef _Ret_maybenull_ JsValueRef(CALLBACK * JsNativeFunction)(_In_ JsValueRef callee, _In_ bool isConstructCall, _In_ JsValueRef *arguments, _In_ unsigned short argumentCount, _In_opt_ void *callbackState);
```
### Parameters 
* __callee__: The JavaScript callee.
* __isConstructCall__: Indicates whether this is a regular call or a 'new' call.
* __arguments__: The arguments to the call. arguments[0] is `this` or `undefined` if the function is called plainly. 
* __argumentCount__: The number of arguments.
* __callbackState__: The state passed to **JsCreateFunction**.

### Return Value 
The result of the call, if any.
