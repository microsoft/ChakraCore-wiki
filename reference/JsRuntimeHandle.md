A handle to a Chakra runtime.
### Syntax 
```
typedef void *JsRuntimeHandle;
```
### Remarks 
Each Chakra runtime has its own independent execution engine, JIT compiler, and garbage collected heap. As such, each runtime is completely isolated from other runtimes.
