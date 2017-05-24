_This is a living document containing ChakraCore team's current priorities as well as release notes for previous releases. Last updated 5/23/17._ 

All the changes done in the public repository flow into Chakra and Microsoft Edge on a regular basis as described in the [Contribution guidelines](https://github.com/Microsoft/ChakraCore/blob/master/CONTRIBUTING.md).

# Future

The following is a summary of the ChakraCore team's backlog for the next 6 months. Some completed items (either in a release or master branch) are included to provide the context and progress of the work.

## Enhancing Host & Platform Support 
* **Node.js**
  * [x] Update [Node.js+ChakraCore](https://github.com/nodejs/node-chakracore) to include [ChakraCore 1.4](https://github.com/Microsoft/ChakraCore/tree/release/1.4)
  * [x] Enable Node-ChakraCore on Mac and Linux.
  * [ ] Support Chrome Debug Protocol in Node-ChakraCore.
  * [ ] Enable Time Travel Debugging over Chrome Debug Protocol using VSCode
  * [ ] Support N-API
  * [ ] Improve Node-ChakraCore performance based on benchmarks and real-world scenarios

* **Cross-platform**
  * [x] Enable ChakraCore interpreter on Linux/OSX
  * [x] Enable JIT on Linux/OSX
  * [x] Enable concurrent GC on Linux/OSX
  * [x] Enable partial GC on Linux/OSX
  * [ ] Enable Intl on Linux/OSX
  * [ ] Match Windows-ChakraCore on test262
  * [ ] Ensure Linux/OSX perf is fully on par with Windows

* **Embedding**
  * [ ] Provide better debugging experience for ChakraCore embedders
    * [ ] Factor CrDP debugging shim in NodeChakraCore as a library to help enable debugging in applications embedding ChakraCore
  * [ ] Enable profiling

## Language Innovation & Standards
* [ ] Support WebAssembly MVP
  * [x] Support MVP features behind experimental flag
  * [ ] Enable MVP on by default
* [ ] Enable post-MVP WebAssembly feautures
  * [ ] Threads
* [ ] Enable WebAssembly debugging
* [ ] Complete module implementation (ES6)
* [ ] Complete Shared Memory and Atomics implementation

## Performance - Staying Fast and Lean
* [ ] Optimize obj[propertyString] style references
* [ ] Optimize hasOwnProperties calls within for…in
* [ ] Optimize Array.isArray
* [ ] Optimize try/finally
* [ ] Optimize code generation for string[index] uses

## Engineering Improvements
* [ ] Enable easier authoring of JavaScript built-ins in JavaScript.

# Release Notes

## ChakraCore 1.4

### [v1.4.4](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.4)

This patch release of ChakraCore 1.4 includes the following security fixes:

- Change to address CVE-2017-0229, CVE-2017-0223, CVE-2017-0224, CVE-2017-0252, CVE-2017-0230, CVE-2017-0234, CVE-2017-0235, CVE-2017-0236, CVE-2017-0228, CVE-2017-0238, CVE-2017-0266
[#2959](https://github.com/Microsoft/ChakraCore/pull/2959)

### [v1.4.3](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.3)
 
This patch release of ChakraCore 1.4 includes the following fixes:
- Change to address CVE-2017-0093 and CVE-2017-0208 [#2834](https://github.com/Microsoft/ChakraCore/pull/2834)
- Internal fixes in Windows 10 Creators Update [#2826](https://github.com/Microsoft/ChakraCore/pull/2826)

### [v1.4.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.2)

This patch release of ChakraCore 1.4 includes the following security fixes:
- Change to address CVE-2017-0067, CVE-2017-0150, CVE-2017-0138, CVE-2017-0094, CVE-2017-0132, CVE-2017-0133, CVE-2017-0134, CVE-2017-0137, CVE-2017-0071, CVE-2017-0151, CVE-2017-0141, CVE-2017-0196, CVE-2017-0136, CVE-2017-0152, CVE-2017-0010, CVE-2017-0035, CVE-2017-0015, CVE-2017-0028
[#2697](https://github.com/Microsoft/ChakraCore/pull/2697)

### [v1.4.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.1)

This patch release of ChakraCore 1.4 enables using ChakraCore [NuGet packages](https://github.com/Microsoft/ChakraCore/wiki/NuGet-Packages) for developing .NET and native applications ([#2266](https://github.com/Microsoft/ChakraCore/pull/2266), [#85](https://github.com/Microsoft/ChakraCore/issues/85)) and includes other bug fixes.

### [v1.4.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.0)

ChakraCore 1.4.0 includes cross-platform JIT support and experimental WebAssembly support along with other language, performance and JSRT updates. See notable changes below.
 
- ChakraCore JIT on Linux and MacOS [#1591](https://github.com/Microsoft/ChakraCore/pull/1591) [#1744](https://github.com/Microsoft/ChakraCore/pull/1744)
- Enhance [Time Travel Debugging](https://github.com/nodejs/node-chakracore/blob/59950ad1e86fee5b872d203adc1929795ff63428/TTD-README.md) support
- Enable [Async Functions](https://tc39.github.io/ecmascript-asyncawait/#async-function-definitions) by default [#1691](https://github.com/Microsoft/ChakraCore/pull/1691)
- Enable [SharedArrayBuffer](https://github.com/tc39/ecmascript_sharedmem) under experimental flag [#1759](https://github.com/Microsoft/ChakraCore/pull/1759)
- Enable WebAssembly [browser preview](http://webassembly.org/roadmap/) support under experimental flag [#1985](https://github.com/Microsoft/ChakraCore/pull/1985)
- Update JSRT String APIs (experimental) [#1830](https://github.com/Microsoft/ChakraCore/pull/1830) 
- Memory reduction through function body redeferral [#1585](https://github.com/Microsoft/ChakraCore/pull/1585)
- Add out-of-process JIT support in Microsoft Edge [#1561](https://github.com/Microsoft/ChakraCore/pull/1561)

## ChakraCore 1.3

### [v1.3.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.3.2)

This patch release of ChakraCore 1.3 includes the following security fixes:

- Change to address bad binding of async arrow function parameters [#2219](https://github.com/Microsoft/ChakraCore/pull/2219)
- All fixes included in [v1.2.3](#v123)

### [v1.3.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.3.1)

This patch release of ChakraCore 1.3 includes the following security fixes:

- Change to address CVE-2016-7207 [#1979](https://github.com/Microsoft/ChakraCore/pull/1979)
- All fixes included in [v1.2.2](#v122)

### [v1.3.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.3.0)

Release 1.3.0 includes experimental support on x64 Linux/OSX, experimental JSRT debugging APIs,
and other language and performance updates. See notable changes below.

#### Cross-platform
- ChakraCore interpreter and runtime on x64 Linux (still working on JIT or concurrent/partial GC)
- ChakraCore interpreter and runtime on x64 OSX (still working on  JIT or concurrent/partial GC)
[#1134](https://github.com/Microsoft/ChakraCore/pull/1134)

#### Language
- Enable [Symbol.toStringTag](http://www.ecma-international.org/ecma-262/6.0/#sec-symbol.tostringtag)
by default [#1383](https://github.com/Microsoft/ChakraCore/pull/1383)
- Enable [String.prototype.padStart](https://tc39.github.io/ecma262/#sec-string.prototype.padstart)
and [String.prototype.padEnd](https://tc39.github.io/ecma262/#sec-string.prototype.padend)
by default [#1257](https://github.com/Microsoft/ChakraCore/pull/1257)
- Enable [Symbol.prototype[@@toPrimitive]](http://www.ecma-international.org/ecma-262/6.0/#sec-symbol.prototype-@@toprimitive) and [Date.prototype[@@toPrimitive]](http://www.ecma-international.org/ecma-262/6.0/#sec-date.prototype-@@toprimitive)
under experimental flag [#1319](https://github.com/Microsoft/ChakraCore/pull/1319)
- Enable [Symbol.isConcatSpreadable](http://www.ecma-international.org/ecma-262/6.0/#sec-symbol.isconcatspreadable)
under experimental flag [#1198](https://github.com/Microsoft/ChakraCore/pull/1198)
- Enable [Symbol.hasInstance](http://www.ecma-international.org/ecma-262/6.0/#sec-symbol.hasinstance)
under experimental flag [#1063](https://github.com/Microsoft/ChakraCore/pull/1063)

#### Performance
- Optimize creation of Heap arguments object
([`91e0e91`](https://github.com/Microsoft/ChakraCore/commit/91e0e91288ecadcfc01a41f2f0c7e878d2f3ee1a))
- Add fastpath for when Object.hasOwnProperty returns true
[#1449](https://github.com/Microsoft/ChakraCore/pull/1449)
- Enable script function inlining in jitted loop bodies
[#1182](https://github.com/Microsoft/ChakraCore/pull/1182)

#### JSRT
- JSRT Debugging APIs (experimental)
[#926](https://github.com/Microsoft/ChakraCore/pull/926)
- JSRT Module API (experimental)
[#1254](https://github.com/Microsoft/ChakraCore/pull/1254)

#### Test
- Introduce C++ unit testing mechanism using Catch
[#1224](https://github.com/Microsoft/ChakraCore/pull/1224)

## ChakraCore 1.2

### [v1.2.3](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.3)

This patch release of ChakraCore 1.2 includes the following security fixes:

- Change to address CVE-2016-7287,CVE-2016-7286,CVE-2016-7288,CVE-2016-7296
[#2230](https://github.com/Microsoft/ChakraCore/pull/2230)

### [v1.2.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.2)

This patch release of ChakraCore 1.2 includes the following security fixes:

- Change to address CVE-2016-7200, CVE-2016-7201, CVE-2016-720, CVE-2016-7203,
CVE-2016-7208, CVE-2016-7240, CVE-2016-7241, CVE-2016-7242, CVE-2016-7243
[#1942](https://github.com/Microsoft/ChakraCore/pull/1982)

### [v1.2.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.1)

This patch release of ChakraCore 1.2 includes the following security fixes:

- Fixed Address deref issue
[#1530](https://github.com/Microsoft/ChakraCore/pull/1530)
- Combined fixes for CVE-2016-3350, CVE-2016-3377 and a defense in depth change in the CustomHeap
([`24c4d7d`](https://github.com/Microsoft/ChakraCore/commit/24c4d7df8199b27d360323ce3be1d7959fd918eb))
- Changes addressing CVE_2016-3382, CVE-2016-3385, CVE-2016-3386, CVE-2016-3389, CVE-2016-3390,
CVE-2016-7189, and a mitigation of a CFG bypass.
([`f05c42e`](https://github.com/Microsoft/ChakraCore/commit/f05c42e64c3b2d057ae1a52fe1917af26c9f2737))

### [v1.2.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.0.0)

- Turn support for [ES2015 Destructuring Assignment](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for [ES2015 Default Parameters](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for the proposed ECMAScript [Exponentiation Operator](https://github.com/rwaldron/exponentiation-operator) on by default
- Enable proposed ECMAScript [Async Functions](https://github.com/tc39/ecmascript-asyncawait) behind an experimental flag
- Enable [ES2015 Modules](http://www.ecma-international.org/ecma-262/6.0/index.html) behind an experimental flag
- Includes multiple changes to reduce memory consumption
