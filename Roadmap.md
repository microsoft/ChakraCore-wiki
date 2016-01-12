_This is a living document. It describes the priorities as they exist today but can evolve over time._

The ChakraCore team is committed to working in the open. We implement new capabilities in public forks. All the changes done in the public repository flow into Chakra and Microsoft Edge on a regular basis as described in the [Contribution guidelines](https://github.com/Microsoft/ChakraCore/blob/master/CONTRIBUTING.md). The following is a summary of the ChakraCore team’s backlog for the next 6 months (through June 2016). 

# Enhancing Host & Platform Support 
* Node.js: Submit pull request to Node.js to include ChakraCore sources and the ChakraCore-V8 shim
* Cross-platform: An implementation of ChakraCore interpreter and runtime, no JIT, on Linux. Targeting x64 Ubuntu 15.10. This could change based on customer feedback.
  * Produce a build configuration of ChakraCore that does not include the JIT compiler
  * Publish a branch that establishes development environment 
  * Get lib\common\codex to compile
  * Get lib\common to build (solve the string problem)
  * Get GC host app to build and run (no concurrency and no partial collections)
  * Get lib\runtime\base directory to compile
  * Get lib\Parser to compile
  * Write simple parser host to print AST
  * Get lib\runtime\bytecode directory to compile
  * Get lib\runtime\library directory to compile
  * Get lib\runtime\language directory to compile, rewrite assembly portions
  * Make it link
  * Make it run

# Language Innovation & Standards


# Performance – Staying Fast and Lean


# Diagnostics & Tooling Enhancements


# Engineering Improvements

* Acceptance of a pull request to Node.js mainline to include ChakraCore
* Turn support for [async functions](https://github.com/tc39/ecmascript-asyncawait) on by default
* Turn support for ES2015 destructuring on by default
* Turn support for the [exponentiation operator](https://github.com/rwaldron/exponentiation-operator) on by default
* Modern debug APIs that can easily be bridged to the V8 debug protocol
* ES2015 modules behind an experimental flag
* Introduce C++ unit testing mechanism. Plan is to use moswald's xUnit++
* An implementation of ChakraCore on Linux
  * Produce a build configuration of ChakraCore that does not include the JIT
  * Construct a branch that establishes the patterns that the team wants to see used in the port. We want to end up with something maintainable.
* Time travel debugging working in Node.js
* Decode WebAssembly binaries into ASM.JS bytecode and execute using ASM.JS pipeline

We have not yet established a release cadence or criteria for creating a release.