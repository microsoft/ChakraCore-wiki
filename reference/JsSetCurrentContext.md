Sets the current script context on the thread. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsSetCurrentContext(
    _In_ JsContextRef context);
```
### Parameters 
* __context__: The script context to make current.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
