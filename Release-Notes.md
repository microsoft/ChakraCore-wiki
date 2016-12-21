# ChakraCore 1.4

## [v1.4.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.4.0)

ChakraCore 1.4.0 includes cross-platform JIT support and experimental WebAssembly support along with other language, performance and JSRT updates. See notable changes below.
 
- ChakraCore JIT on Linux and MacOS [#1591](https://github.com/Microsoft/ChakraCore/pull/1591) [#1744](https://github.com/Microsoft/ChakraCore/pull/1744)
- Enhance [Time Travel Debugging](https://github.com/nodejs/node-chakracore/blob/59950ad1e86fee5b872d203adc1929795ff63428/TTD-README.md) support
- Enable [Async Functions](https://tc39.github.io/ecmascript-asyncawait/#async-function-definitions) by default [#1691](https://github.com/Microsoft/ChakraCore/pull/1691)
- Enable [SharedArrayBuffer](https://github.com/tc39/ecmascript_sharedmem) under experimental flag [#1759](https://github.com/Microsoft/ChakraCore/pull/1759)
- Enable WebAssembly [browser preview](http://webassembly.org/roadmap/) support under experimental flag [#1985](https://github.com/Microsoft/ChakraCore/pull/1985)
- Update JSRT String APIs (experimental) [#1830](https://github.com/Microsoft/ChakraCore/pull/1830) 
- Memory reduction through function body redeferral [#1585](https://github.com/Microsoft/ChakraCore/pull/1585)
- Add out-of-process JIT support in Microsoft Edge [#1561](https://github.com/Microsoft/ChakraCore/pull/1561)

# ChakraCore 1.3

## [v1.3.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.3.1)

This patch release of ChakraCore 1.3 includes the following security fixes:

- Change to address CVE-2016-7207 [#1979](https://github.com/Microsoft/ChakraCore/pull/1979)
- All fixes included in [v1.2.2](#v122)

## [v1.3.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.3.0)

Release 1.3.0 includes experimental support on x64 Linux/OSX, experimental JSRT debugging APIs,
and other language and performance updates. See notable changes below.

### Cross-platform
- ChakraCore interpreter and runtime on x64 Linux (still working on JIT or concurrent/partial GC)
- ChakraCore interpreter and runtime on x64 OSX (still working on  JIT or concurrent/partial GC)
[#1134](https://github.com/Microsoft/ChakraCore/pull/1134)

### Language
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

### Performance
- Optimize creation of Heap arguments object
([`91e0e91`](https://github.com/Microsoft/ChakraCore/commit/91e0e91288ecadcfc01a41f2f0c7e878d2f3ee1a))
- Add fastpath for when Object.hasOwnProperty returns true
[#1449](https://github.com/Microsoft/ChakraCore/pull/1449)
- Enable script function inlining in jitted loop bodies
[#1182](https://github.com/Microsoft/ChakraCore/pull/1182)

### JSRT
- JSRT Debugging APIs (experimental)
[#926](https://github.com/Microsoft/ChakraCore/pull/926)
- JSRT Module API (experimental)
[#1254](https://github.com/Microsoft/ChakraCore/pull/1254)

### Test
- Introduce C++ unit testing mechanism using Catch
[#1224](https://github.com/Microsoft/ChakraCore/pull/1224)

# ChakraCore 1.2

## [v1.2.2](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.2)

This patch release of ChakraCore 1.2 includes the following security fixes:

- Change to address CVE-2016-7200, CVE-2016-7201, CVE-2016-720, CVE-2016-7203,
CVE-2016-7208, CVE-2016-7240, CVE-2016-7241, CVE-2016-7242, CVE-2016-7243
[#1942](https://github.com/Microsoft/ChakraCore/pull/1982)

## [v1.2.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.1)

This patch release of ChakraCore 1.2 includes the following security fixes:

- Fixed Address deref issue
[#1530](https://github.com/Microsoft/ChakraCore/pull/1530)
- Combined fixes for CVE-2016-3350, CVE-2016-3377 and a defense in depth change in the CustomHeap
([`24c4d7d`](https://github.com/Microsoft/ChakraCore/commit/24c4d7df8199b27d360323ce3be1d7959fd918eb))
- Changes addressing CVE_2016-3382, CVE-2016-3385, CVE-2016-3386, CVE-2016-3389, CVE-2016-3390,
CVE-2016-7189, and a mitigation of a CFG bypass.
([`f05c42e`](https://github.com/Microsoft/ChakraCore/commit/f05c42e64c3b2d057ae1a52fe1917af26c9f2737))

## [v1.2.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.0.0)

- Turn support for [ES2015 Destructuring Assignment](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for [ES2015 Default Parameters](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for the proposed ECMAScript [Exponentiation Operator](https://github.com/rwaldron/exponentiation-operator) on by default
- Enable proposed ECMAScript [Async Functions](https://github.com/tc39/ecmascript-asyncawait) behind an experimental flag
- Enable [ES2015 Modules](http://www.ecma-international.org/ecma-262/6.0/index.html) behind an experimental flag
- Includes multiple changes to reduce memory consumption
