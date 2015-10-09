A reference to a script context.
### Syntax 
```
typedef JsRef JsContextRef;
```
### Remarks 
Each script context contains its own global object, distinct from the global object in other script contexts.

Many Chakra hosting APIs require an "active" script context, which can be set using **JsSetCurrentContext**. Chakra hosting APIs that require a current context to be set will note that explicitly in their documentation.