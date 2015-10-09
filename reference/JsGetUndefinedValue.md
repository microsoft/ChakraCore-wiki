Gets the value of **undefined** in the current script context. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetUndefinedValue(
    _Out_ JsValueRef *undefinedValue);
```
### Parameters 
* __undefinedValue__: The **undefined** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
