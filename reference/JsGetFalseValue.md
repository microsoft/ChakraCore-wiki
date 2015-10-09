Gets the value of **false** in the current script context. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetFalseValue(
    _Out_ JsValueRef *falseValue);
```
### Parameters 
* __falseValue__: The **false** value.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
Requires an active script context.
