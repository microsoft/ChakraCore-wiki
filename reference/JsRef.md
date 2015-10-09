A reference to an object owned by the Chakra garbage collector.
### Syntax 
```
typedef void *JsRef;
```
### Remarks 
A Chakra runtime will automatically track **JsRef** references as long as they are stored in local variables or in parameters (i.e. on the stack). Storing a **JsRef** somewhere other than on the stack requires calling **JsAddRef** and **JsRelease** to manage the lifetime of the object, otherwise the garbage collector may free the object while it is still in use.