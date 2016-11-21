Create JavascriptString variable from Utf8 string
### Syntax 
```
CHAKRA_API
       JsCreateStringUtf8(
        _In_ const uint8_t *content,
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
Input string can be either ASCII or Utf8
