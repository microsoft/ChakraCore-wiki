Write JavascriptString value into C string buffer (Utf8)
### Syntax 
```
CHAKRA_API
    JsCopyString(
        _In_ JsValueRef value,
        _Out_opt_ char* buffer,
        _In_ size_t bufferSize,
        _Out_opt_ size_t* writtenLength,
        _Out_opt_ size_t* actualLength);
```
### Parameters 
* __value__: JavascriptString value
* __buffer__: Pointer to buffer
* __bufferSize__: Buffer size
* __writtenLength__: Total number of UTF8 decoded bytes written. This is only populated when passed with non-null `buffer`,else is set to 0.
* __actualLength__: Total number of UTF8 decoded bytes present in `value`.  Useful to initialize buffer of appropriate size that can be passed in to this API.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**

When size of the `buffer` is unknown, `buffer` argument can be nullptr.
In that case, `actualLength` argument will return the length needed to accomodate all the UTF8 decoded bytes present in `value`.
`writtenLength` will only get populated when valid `buffer` is passed as argument.