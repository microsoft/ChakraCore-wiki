### Ch CLI shell

The ch CLI shell is used for internal testing of Chakra Core but can be used as a standard alone shell with minimal capabilities.
Be aware that it doesn't provide a stable hosting API so it can change from one release to another.

### Basic usage

```
ch [-v|-version] [-h|-help|-?] <source file> [options]
```

### Common options

* `-args` and `-endargs` Used to pass arguments to the script. They can be consumed using the `WScript.Arguments` array object.

### Host APIs

* `WScript.LoadScriptFile` Loads a JS script from the file system. It takes relative paths to CWD.

For a complete and current list of available API, take a look at the [WScriptJsrt:Initialize function](https://github.com/Microsoft/ChakraCore/blob/master/bin/ch/WScriptJsrt.cpp#L916)
