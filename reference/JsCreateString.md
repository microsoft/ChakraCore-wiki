Create JavascriptString variable from C string
### Syntax 
```
CHAKRA_API
    JsCreateString(
        _In_ const char *content,
        _In_ size_t length,
        _Out_ JsValueRef *value);
```
### Parameters 
* __content__: Pointer to string memory.
* __length__: Number of bytes within the string
* __value__: JsValueRef representing the JavascriptString


### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
C string is expected to be ASCII
