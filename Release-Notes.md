# 1.2

## [v1.2.1](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.1)

Security Fixes:

- [PR #1530](Microsoft/ChakraCore/pulls/1530) ([`5ec2d8f`](https://github.com/Microsoft/ChakraCore/commit/5ec2d8f6dd3e67e8aa85002dbad152a614f92eeb)) Fixed Address deref issue
- ([`24c4d7d`](https://github.com/Microsoft/ChakraCore/commit/24c4d7df8199b27d360323ce3be1d7959fd918eb)) Combined fixes for CVE-2016-3350, CVE-2016-3377 and a defense in depth change in the CustomHeap
- ([`f05c42e`](https://github.com/Microsoft/ChakraCore/commit/f05c42e64c3b2d057ae1a52fe1917af26c9f2737)) Changes addressing CVE_2016-3382, CVE-2016-3385, CVE-2016-3386, CVE-2016-3389, CVE-2016-3390, CVE-2016-7189, and a mitigation of a CFG bypass.

## [v1.2.0](https://github.com/Microsoft/ChakraCore/releases/tag/v1.2.0.0)

- Turn support for [ES2015 Destructuring Assignment](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for [ES2015 Default Parameters](http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
- Turn support for the proposed ECMAScript [Exponentiation Operator](https://github.com/rwaldron/exponentiation-operator) on by default
- Enable proposed ECMAScript [Async Functions](https://github.com/tc39/ecmascript-asyncawait) behind an experimental flag
- Enable [ES2015 Modules](http://www.ecma-international.org/ecma-262/6.0/index.html) behind an experimental flag
- Includes multiple changes to reduce memory consumption
