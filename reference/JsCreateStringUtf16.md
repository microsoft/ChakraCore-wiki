Create JavascriptString variable from Utf16 string
### Syntax 
```
CHAKRA_API
    JsCreateStringUtf16(
        _In_ const uint16_t *content,
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
**This API is experimental and may have breaking change later.** 

Expects Utf16 string.
