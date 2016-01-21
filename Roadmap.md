_This is a living document. It describes the priorities as they exist today but can evolve over time._

The ChakraCore team is committed to working in the open. We implement new capabilities in public forks. All the changes done in the public repository flow into Chakra and Microsoft Edge on a regular basis as described in the [Contribution guidelines](https://github.com/Microsoft/ChakraCore/blob/master/CONTRIBUTING.md). The following is a summary of the ChakraCore team’s backlog for the next 6 months (through June 2016). 

# Enhancing Host & Platform Support 
* **Node.js**: Submit pull request to Node.js to include ChakraCore sources and the ChakraCore-V8 shim
* **Cross-platform**: An implementation of ChakraCore interpreter and runtime, no JIT, on Linux, targeting x64 Ubuntu 15.10 (JIT and support for more platforms to come in future iterations). This could change based on customer feedback.
  * [x] Produce a build configuration of ChakraCore that does not include the JIT compiler
  * [x] Publish a branch that establishes development environment 
  * [x] Get lib\common\codex to compile
  * [...] Get lib\common to build
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
* Continue TC39 and WebAssembly standardization engagements
* Turn support for [ES2015 Destructuring Assignment] (http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
* Turn support for [ES2015 Default Parameters] (http://www.ecma-international.org/ecma-262/6.0/index.html) on by default
* Turn support for the proposed ECMAScript [Exponentiation Operator] (https://github.com/rwaldron/exponentiation-operator) on by default
* Turn support for the proposed ECMAScript [Async Functions] (https://github.com/tc39/ecmascript-asyncawait) on by default
* Enable [ES2015 Modules] (http://www.ecma-international.org/ecma-262/6.0/index.html) behind an experimental flag
* Decode WebAssembly binaries into ASM.JS bytecode and execute using ASM.JS pipeline

# Performance – Staying Fast and Lean
* Analyze Chakra’s memory footprint on real-world sites and reduce the same. Easiest target is to shrink FunctionBody. Analyze the possibility of throwing out byte code for JIT’ed functions.
* Implement “native fields” optimization - the capability of storing some properties as unwrapped objects on objects

# Diagnostics & Tooling Enhancements
* Implement flat C debugging APIs following the existing JSRT pattern that can easily be bridged to the V8 debug protocol
* Demonstrate Visual Studio Code debugging Node.js+ChakraCore
* Integrate Time Travel Debugging implementation into master
  * Review and agree on JSRT API shape
* Flesh out TTD plumbing in ChakraCore-V8 shim/Node.js to allow record in Node.js and playback in ch.exe

# Engineering Improvements
* Introduce C++ unit testing mechanism. Evaluating moswald's xUnit++ and [Criterion](https://github.com/Snaipe/Criterion)
* Move JSRT API unit tests from internal testing mechanism to new framework.
* Establish a criteria and release cadence for creating public releases for ChakraCore