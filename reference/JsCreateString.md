Create JavascriptString variable from ASCII or Utf8 string
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
**This API is experimental and may have breaking change later.** Input string can be either ASCII or Utf8.