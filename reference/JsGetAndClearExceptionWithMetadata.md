Returns metadata relating to the exception that caused the runtime of the current context
to be in the exception state and resets the exception state for that runtime. The metadata
includes a reference to the exception itself.

### Syntax 
```
CHAKRA_API
    JsGetAndClearExceptionWithMetadata(
        _Out_ JsValueRef *metadata);
```

### Parameters 
* __metadata__: The exception metadata for the runtime of the current context.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.

### Remarks 
**This API is experimental and may have breaking change later.** 

If the runtime of the current context is not in an exception state, this API will return
__JsErrorInvalidArgument__. If the runtime is disabled, this will return an exception
indicating that the script was terminated, but it will not clear the exception (the
exception will be cleared if the runtime is re-enabled using
__JsEnableRuntimeExecution__).

The metadata value is a javascript object with the following properties: __exception__, the
thrown exception object; __line__, the 0 indexed line number where the exception was thrown;
__column__, the 0 indexed column number where the exception was thrown; __length__, the
source-length of the cause of the exception; __source__, a string containing the line of
source code where the exception was thrown; and __url__, a string containing the name of
the script file containing the code that threw the exception.

Requires an active script context.