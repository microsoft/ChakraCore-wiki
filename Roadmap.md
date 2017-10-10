_This is a living document containing ChakraCore team's current priorities as well as release notes for previous releases. Future roadmap last updated 8/18/17._ 

All the changes done in the public repository flow into Chakra and Microsoft Edge on a regular basis as described in the [Contribution guidelines](https://github.com/Microsoft/ChakraCore/blob/master/CONTRIBUTING.md).

(Scroll to [Release Notes](#release-notes))

# Future

The following is a summary of the ChakraCore team's backlog for the next 6 months. Some completed items (either in a release or master branch) are included to provide the context and progress of the work.

## Enhancing Host & Platform Support 
* **Node.js**
  * [x] Update [Node.js+ChakraCore](https://github.com/nodejs/node-chakracore) to include [ChakraCore 1.4](https://github.com/Microsoft/ChakraCore/tree/release/1.4)
  * [x] Enable Node-ChakraCore on Mac and Linux.
  * [x] Support Chrome Debug Protocol in Node-ChakraCore.
  * [x] Enable Time Travel Debugging over Chrome Debug Protocol using VSCode
  * [x] Support N-API
  * [ ] Improve Node-ChakraCore performance based on benchmarks and real-world scenarios

* **Cross-platform**
  * [x] Enable ChakraCore interpreter on Linux/OSX
  * [x] Enable JIT on Linux/OSX
  * [x] Enable concurrent GC on Linux/OSX
  * [x] Enable partial GC on Linux/OSX
  * [ ] Enable Intl on Linux/OSX
  * [ ] Match Windows-ChakraCore on test262
  * [x] Ensure Linux/OSX perf is fully on par with Windows

* **Embedding**
  * [ ] Provide better debugging experience for ChakraCore embedders
    * [ ] Factor CrDP debugging shim in NodeChakraCore as a library to help enable debugging in applications embedding ChakraCore
  * [ ] Enable profiling

## Language Innovation & Standards
* [x] Support WebAssembly MVP
  * [x] Support MVP features behind experimental flag
  * [x] Enable MVP on by default
* [ ] Enable post-MVP WebAssembly features
  * [ ] Threads
* [ ] Enable WebAssembly debugging
* [x] Complete module implementation (ES6)
* [x] Complete Shared Memory and Atomics implementation

## Performance - Staying Fast and Lean
* [x] Optimize obj[propertyString] style references
* [x] Optimize hasOwnProperties calls within for…in
* [x] Optimize Array.isArray
* [x] Optimize try/finally
* [ ] Optimize code generation for string[index] uses

## Engineering Improvements
* [ ] Enable easier authoring of JavaScript built-ins in JavaScript.

# Release Notes

## ChakraCore 1.7

### [v1.7.3](https://github.com/Microsoft/ChakraCore/releases/tag/v1.7.3)
This patch release of ChakraCore 1.7 includes security fixes, performance improvements, and bugfixes.

#### Security
- Change to address CVE-2017-11792, CVE-2017-11796, CVE-2017-11797, CVE-2017-11799, CVE-2017-11801, CVE-2017-11802, CVE-2017-11805, CVE-2017-11806, CVE-2017-11807, CVE-2017-11808, CVE-2017-11809, CVE-2017-11811, CVE-2017-11812, CVE-2017-11821 [#3917](https://github.com/Microsoft/ChakraCore/pull/3917)

### [v1.7.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.7.2)

This patch release of ChakraCore 1.7 includes security fixes, performance improvements, and bugfixes.

#### Security
- Change to address CVE-2017-8741, CVE-2017-8748, CVE-2017-11767, CVE-2017-8756, CVE-2017-8753, CVE-2017-8729, CVE-2017-8739, CVE-2017-8751, CVE-2017-8757, CVE-2017-11764, CVE-2017-8660, CVE-2017-8755, CVE-2017-8649, CVE-2017-8740, CVE-2017-8752 [#3729](https://github.com/Microsoft/ChakraCore/pull/3729)

### [v1.7.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.7.1)

This patch release of ChakraCore 1.7 includes security fixes, performance improvements and JSRT API changes. See notable changes below.

#### Security
- Change to address CVE-2017-0228, CVE-2017-8634, CVE-2017-8635, CVE-2017-8636, CVE-2017-8637, CVE-2017-8638, CVE-2017-8640, CVE-2017-8641, CVE-2017-8645, CVE-2017-8646, CVE-2017-8647, CVE-2017-8655, CVE-2017-8656, CVE-2017-8657, CVE-2017-8658, CVE-2017-8659, CVE-2017-8670, CVE-2017-8671, CVE-2017-8672, CVE-2017-8674 [#3509](https://github.com/Microsoft/ChakraCore/pull/3509)

#### Performance
- Remove tzdata sync calls on xplat [#3420](https://github.com/Microsoft/ChakraCore/pull/3420)

#### JSRT
- Add [JsGetDataViewInfo](https://github.com/Microsoft/ChakraCore/wiki/JsGetDataViewInfo) [#3462](https://github.com/Microsoft/ChakraCore/pull/3462)
- Modify [JsCopyString](https://github.com/Microsoft/ChakraCore/wiki/JsCopyString) to return actual count of utf8 bytes [#3433](https://github.com/Microsoft/ChakraCore/pull/3433)


### [v1.7.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.7.0)

ChakraCore 1.7.0 includes performance improvements and support for building Node-ChakraCore with link-time optimizations. It adds the following new JSRT APIs:

- [JsHasOwnProperty](https://github.com/Microsoft/ChakraCore/wiki/JsHasOwnProperty) [#3316](https://github.com/Microsoft/ChakraCore/pull/3316).
- [JsCopyStringOneByte](https://github.com/Microsoft/ChakraCore/wiki/JsCopyStringOneByte) [#3408](https://github.com/Microsoft/ChakraCore/pull/3408).

## ChakraCore 1.6

### [v1.6.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.6.2)

This patch release of ChakraCore 1.6 includes the following security fixes:

#### Security
- Change to address CVE-2017-8741, CVE-2017-8748, CVE-2017-11767, CVE-2017-8756, CVE-2017-8753, CVE-2017-8729, CVE-2017-8739, CVE-2017-8751, CVE-2017-8757, CVE-2017-11764, CVE-2017-8660, CVE-2017-8755, CVE-2017-8649, CVE-2017-8740, CVE-2017-8752 [#3729](https://github.com/Microsoft/ChakraCore/pull/3729)

### [v1.6.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.6.1)

This patch release of ChakraCore 1.6 includes security fixes and bug fixes. See notable changes below.

#### Security
- Change to address CVE-2017-0228, CVE-2017-8634, CVE-2017-8635, CVE-2017-8636, CVE-2017-8637, CVE-2017-8638, CVE-2017-8640, CVE-2017-8641, CVE-2017-8645, CVE-2017-8646, CVE-2017-8647, CVE-2017-8655, CVE-2017-8656, CVE-2017-8657, CVE-2017-8658, CVE-2017-8659, CVE-2017-8670, CVE-2017-8671, CVE-2017-8672, CVE-2017-8674 [#3509](https://github.com/Microsoft/ChakraCore/pull/3509)

### [v1.6.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.6.0)

ChakraCore 1.6.0 includes more JavaScript and WebAssembly feature updates and performance enhancements. See notable changes below.

#### Language
- Enable WebAssembly MVP on by default [#2447](https://github.com/Microsoft/ChakraCore/pull/2447)
- Enable SharedArrayBuffer on by default [#2939](https://github.com/Microsoft/ChakraCore/pull/2939)
- Enable [dynamic module import](https://github.com/tc39/proposal-dynamic-import) [#2913](https://github.com/Microsoft/ChakraCore/pull/2913)
- Support ES6 iterators for DOM objects [58ac5aeb7](https://github.com/Microsoft/ChakraCore/commit/58ac5aeb79063bec71aef310e46863001d926410)
- Remove SIMD support in JavaScript [#3296](https://github.com/Microsoft/ChakraCore/pull/3296)

#### Performance
- Support function body (re-)deferral in lexical scopes and parameter scopes [#2666](https://github.com/Microsoft/ChakraCore/pull/2666)
- Use PolymorphicInlineCache for obj[string] pattern [#2883](https://github.com/Microsoft/ChakraCore/pull/2883)
- Enable optimizer on functions with try/finally [#2954](https://github.com/Microsoft/ChakraCore/pull/2954)

## ChakraCore 1.5

### [v1.5.3](https://github.com/Microsoft/ChakraCore/releases/tag/v1.5.3)

This patch release of ChakraCore 1.5 includes the following security fixes:

- Change to address CVE-2017-8598, CVE-2017-8601, CVE-2017-8603, CVE-2017-8604, CVE-2017-8606, CVE-2017-8607, CVE-2017-8608, CVE-2017-8609, CVE-2017-8610, CVE-2017-8619 [#3341](https://github.com/Microsoft/ChakraCore/pull/3341)

### [v1.5.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.5.2)

This patch release of ChakraCore 1.5 includes the following security fixes:

- Change to address CVE-2017-0228, CVE-2017-8499, CVE-2017-8518, CVE-2017-8520, CVE-2017-8522, CVE-2017-8524, CVE-2017-8548 [#3166](https://github.com/Microsoft/ChakraCore/pull/3166)

### [v1.5.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.5.1)

This patch release of ChakraCore 1.5 includes a fix for a handle leak when creating multiple runtimes [#3092](https://github.com/Microsoft/ChakraCore/pull/3092)

### [v1.5.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.5.0)

ChakraCore 1.5.0 includes cross-platform concurrent/partial GC support and a set of new JSRT APIs among other changes. See notable changes below.

- Enable broader software-based write barrier support in ChakraCore GC [#2372](https://github.com/Microsoft/ChakraCore/pull/2372)
- Turn on ChakraCore concurrent/partial GC for Linux/OSX
- New experimental JSRT APIs
    * [JsCreatePromise](https://github.com/Microsoft/ChakraCore/wiki/JsCreatePromise) - add API to create promise [#2594](https://github.com/Microsoft/ChakraCore/pull/2594)
    * [JsGetAndClearExceptionWithMetadata](https://github.com/Microsoft/ChakraCore/wiki/JsGetAndClearExceptionWithMetadata) - add API to clear exception and expose additional information [#2936](https://github.com/Microsoft/ChakraCore/pull/2936)
    * [JsWeakRef](https://github.com/Microsoft/ChakraCore/wiki/JsWeakRef)/[JsCreateWeakReference](https://github.com/Microsoft/ChakraCore/wiki/JsCreateWeakReference)/[JsGetWeakReferenceValue](https://github.com/Microsoft/ChakraCore/wiki/JsGetWeakReferenceValue) - add weak reference APIs [#2948](https://github.com/Microsoft/ChakraCore/pull/2948)

## ChakraCore 1.4

### [v1.4.5](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.5)

This patch release of ChakraCore 1.4 includes a fix for a handle leak when creating multiple runtimes [#3092](https://github.com/Microsoft/ChakraCore/pull/3092).

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
