# ChakraCore Architecture Overview

ChakraCore is split into four main parts: the JSRT embedding APIs, the parser, the engine runtime, and the engine backend.  

## JSRT

For more information on JSRT, see the [[JavaScript Runtime (JSRT) reference]] documentation.

## Parser

The parser handles parsing the standard JavaScript language.

## Runtime

Once parsed, ChakraCore creates a bytecode which is passed to the interpreter.  

The runtime components also cover the JS runtime API, the standard set of JavaScript API calls (eg ```Date.now()```).

## Backend

The ChakraCore backend handles JIT'ing code to various architectures.


TODO TODO TODO Questions:

* Are we missing major components?
* What are the key things to say in each major component?
* What are key subcomponents to cover to understand the codebase? (eg, I know I'm missing lots, including things like "the garbage collector and a brief overview of how it works")
