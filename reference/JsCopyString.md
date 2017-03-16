Write JavascriptString value into C string buffer (Utf8)
### Syntax 
```
CHAKRA_API
       JsCopyString(
        _In_ JsValueRef value,
        _Out_opt_ char* buffer,
        _In_ size_t bufferSize,
        _Out_opt_ size_t* written);
```
### Parameters 
* __value__: JavascriptString value
* __buffer__: Pointer to buffer
* __bufferSize__: Buffer size
* __written__: Total number of characters written

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**
When size of the `buffer` is unknown, `buffer` argument can be nullptr.
In that case, `written` argument will return the length needed.