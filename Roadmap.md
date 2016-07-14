_This is a living document. It describes the priorities as they exist today and will evolve over time._

All the changes done in the public repository flow into Chakra and Microsoft Edge on a regular basis as described in the [Contribution guidelines](https://github.com/Microsoft/ChakraCore/blob/master/CONTRIBUTING.md). The following is a summary of the ChakraCore team's backlog for the next 6 months. Last updated 7/6/16.

# Enhancing Host & Platform Support 
* **Node.js**
  * Update [Node.js+ChakraCore](https://github.com/nodejs/node-chakracore) to include [ChakraCore 1.2](https://github.com/Microsoft/ChakraCore/tree/release/1.2)
  * Implement V8 debug protocol in the Node.js [ChakraShim](https://github.com/nodejs/node-chakracore/tree/chakracore-master/deps/chakrashim) to enable debugging using VS Code.

* **Cross-platform**: (See [#111: \[Discussion\] Linux / Cross-platform planning](https://github.com/Microsoft/ChakraCore/issues/111).) An implementation of ChakraCore interpreter and runtime on Linux, targeting x64 Ubuntu 16.04 LTS and Clang 3.8+
  * [x] Get GC host app to build and run (no concurrency and no partial collections)
  * [x] Get lib\runtime\base directory to compile
  * [x] Get lib\Parser to compile
  * [x] Get lib\runtime\bytecode directory to compile
  * [x] Get lib\runtime\library directory to compile
  * [x] Get lib\runtime\language directory to compile, rewrite assembly portions
  * [x] Make it link
  * [x] Make it run
    * [x] Run hello world
    * [x] Run tests in the Basics directory
    * [x] Run Date-related unit tests
    * [x] Run Exception/Stack-walking related unit tests
    * [x] Run benchmarks
    * [x] Pass all unit tests
  * [ ] Build and pass unit tests on OS X
  * [ ] Enable Jenkins CI support for OS X
  * [ ] Match node-chakracore on xplat
  * [ ] Enable Intl on xplat
  * [ ] Match Windows-ChakraCore on test262
  * [ ] Enable profiling interpreter on xplat
  * [ ] Enable dynamic interpreter thunks on xplat
  * [ ] Enable JIT on xplat
  * [ ] Implement broader software-based write barrier support in the GC
  * [ ] Enable concurrent GC on xplat
  * [ ] Enable partial GC on xplat

# Language Innovation & Standards
- Continue TC39 and WebAssembly standardization engagements
- Begin decoding WebAssembly post-order binary format and converting to ASM.JS bytecode
- Complete module implementation and enable it by default (ES6)
- Eval support in default parameter list  (ES6)
- Well-known symbols: (ES6)
    * Symbol.hasInstance
    * Symbol.toPrimitive
    * Symbol.toStringTag
    * Symbol.isConcatSpreadable
- Shared memory and atomics (ESNext)
- Regex Buffet (ESNext)
    * RegExp named capture groups
    * RegExp lookbehind
- Object.getOwnPropertyDescriptors (ESNext)


# Performance - Staying Fast and Lean
* Implement ability to "re-defer" functions and pitch byte code for already JITted functions.
* Implement "native fields" optimization - the capability of storing some properties as unwrapped objects on objects

# Diagnostics & Tooling Enhancements
* Merge JsRTDebugging branch to master. This branch contains an implementation of flat C debugging APIs following the existing JSRT pattern that can easily be bridged to the V8 debug protocol.
* Integrate Time Travel Debugging implementation into master
  * Review and agree on JSRT API shape
* Enhance the Node.js [ChakraShim](https://github.com/nodejs/node-chakracore/tree/chakracore-master/deps/chakrashim) to enable TTD recording of Node.js and playback using ch.exe.

# Engineering Improvements
* Introduce C++ unit testing mechanism using [Catch](https://github.com/philsquared/Catch)
* Move JSRT API unit tests from internal testing mechanism to new framework.
* Enable easier authoring of JavaScript built-ins in JavaScript.

# Releases
## 1.2
- Turn support for [ES2015 Destructuring Assignment] (http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for [ES2015 Default Parameters] (http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for the proposed ECMAScript [Exponentiation Operator] (https://github.com/rwaldron/exponentiation-operator) on by default
- Enable proposed ECMAScript [Async Functions] (https://github.com/tc39/ecmascript-asyncawait) behind an experimental flag
- Enable [ES2015 Modules] (http://www.ecma-international.org/ecma-262/6.0/index.html) behind an experimental flag
- Includes multiple changes to reduce memory consumption
