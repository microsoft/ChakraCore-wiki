Creates a new JavaScript Promise object.
### Syntax 
```
CHAKRA_API
	JsCreatePromise(
	    _Out_ JsValueRef *promise,
	    _Out_ JsValueRef *resolveFunction,
	    _Out_ JsValueRef *rejectFunction);
```
### Parameters 
* __promise__: The new Promise object.
* __resolveFunction__: The function called to resolve the created Promise object.
* __rejectFunction__: The function called to reject the created Promise object.


### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.** 

Requires an active script context.