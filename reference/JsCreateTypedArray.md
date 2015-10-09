Creates a Javascript typed array object. 
### Syntax 
```
STDAPI_(JsErrorCode)
    JsCreateTypedArray(
    _In_ JsTypedArrayType arrayType,
    _In_ JsValueRef baseArray,
    _In_ unsigned int byteOffset,
    _In_ unsigned int elementLength,
    _Out_ JsValueRef *result);
```
### Parameters 
* __arrayType__: The type of the array to create.
* __baseArray__:  The base array of the new array. Use **JS_INVALID_REFERENCE** if no base array.
* __byteOffset__:  The offset in bytes from the start of baseArray (ArrayBuffer) for result typed array to reference. Only applicable when baseArray is an ArrayBuffer object. Must be 0 otherwise.
* __elementLength__:  The number of elements in the array. Only applicable when creating a new typed array without baseArray (baseArray is **JS_INVALID_REFERENCE**) or when baseArray is an ArrayBuffer object. Must be 0 otherwise.
* __result__: The new typed array object.

### Return Value 
The code **JsNoError** if the operation succeeded, a failure code otherwise.
### Remarks 
The **baseArray** can be an **ArrayBuffer**, another typed array, or a JavaScript
**Array**. The returned typed array will use the baseArray if it is an ArrayBuffer, or
otherwise create and use a copy of the underlying source array.
Requires an active script context.
