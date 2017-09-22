Write JavascriptString value into C string buffer (Utf8)
### Syntax 
```
CHAKRA_API
    JsCopyString(
        _In_ JsValueRef value,
        _Out_opt_ char* buffer,
        _In_ size_t bufferSize,
        _Out_opt_ size_t* length);
```
### Parameters 
* __value__: JavascriptString value
* __buffer__: Pointer to buffer
* __bufferSize__: Buffer size
* __length__: If `buffer` is non-null, then this will be the number of bytes written into the buffer. If `buffer` is null, then this will be the number of bytes required to fit the full string.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**

When size of the `buffer` is unknown, `buffer` argument can be nullptr.
In that case, `length` argument will return the length needed to accommodate all the UTF8 decoded bytes present in `value`.
If `buffer` is non-null and `bufferSize` is too small to fit the full utf8 string, the process will abort.