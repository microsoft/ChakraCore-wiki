Obtains frequently used properties of a data view. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsGetDataViewInfo(
    _In_ JsValueRef dataView,
    _Out_opt_ JsValueRef *arrayBuffer,
    _Out_opt_ unsigned int *byteOffset,
    _Out_opt_ unsigned int *byteLength);
```
### Parameters 
* __dataView__: The data view instance.
* __arrayBuffer__: The ArrayBuffer backstore of the view.
* __byteOffset__: The offset in bytes from the start of arrayBuffer referenced by the view.
* __byteLength__: The number of bytes in the view.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
