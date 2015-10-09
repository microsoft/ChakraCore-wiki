Gets the value of **true** in the current script context. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetTrueValue(
    _Out_ JsValueRef *trueValue);
```
### Parameters 
* __trueValue__: The **true** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
