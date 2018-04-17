The ch CLI is used for internal testing of ChakraCore but can be used as a standalone JS shell host with minimal capabilities.
To facilitate testing, a few host capabilities beyond the scope of ECMAScript standard (e.g. loading files) are also provided in ch.


### Basic usage

```
ch [-v|-version] [-h|-help|-?] <source file> [options]
```

### Common options

* `-args` and `-endargs` Used to pass arguments to the script. They can be consumed using the `WScript.Arguments` array object.

#### Usage example:
test.js:
```js
console.log(WScript.Arguments[0])
console.log(WScript.Arguments[1])
```
execution:
```
$ ch test.js -args hello world -endargs
hello
world
```

### Host APIs

* `WScript.LoadScriptFile` Loads a JS script from the file system. It takes relative paths to CWD.

For a complete and current list of available APIs, take a look at the [WScriptJsrt:Initialize function](https://github.com/Microsoft/
Core/blob/master/bin/ch/WScriptJsrt.cpp)
