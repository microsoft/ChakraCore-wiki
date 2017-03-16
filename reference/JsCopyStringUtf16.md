Write string value into Utf16 string buffer
### Syntax 
```
CHAKRA_API
    JsCopyStringUtf16(
        _In_ JsValueRef value,
        _In_ int start,
        _In_ int length,
        _Out_opt_ uint16_t* buffer,
        _Out_opt_ size_t* written);
```
### Parameters 
* __value__: JavascriptString value
* __start__: Start offset of buffer
* __length__: Length to be written
* __buffer__: Pointer to buffer
* __written__: Total number of characters written

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.**

When size of the `buffer` is unknown, `buffer` argument can be nullptr.
In that case, `written` argument will return the length needed.

When start is out of range or < 0, returns JsErrorInvalidArgument
and `written` will be equal to 0. If calculated length is 0 (It can be due to string length or `start`
and length combination), then `written` will be equal to 0 and call
returns JsNoError.
