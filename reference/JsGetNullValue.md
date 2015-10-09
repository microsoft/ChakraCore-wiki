Gets the value of **null** in the current script context. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetNullValue(
    _Out_ JsValueRef *nullValue);
```
### Parameters 
* __nullValue__: The **null** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
