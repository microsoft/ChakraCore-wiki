## Summary of Directory Structure
<pre>
[Root]                        (Introduction documentations, Jenkins scripts etc.) 
|-- Lib 
    |-- Common 
        |-- Codex             (UTF8 conversion utilities) 
        |-- Core              (Core supporting utilities) 
        |-- Exceptions        (Exceptions classes and utilities) 
        |-- DataStructures    (Link list, Dictionary, etc.) 
        |-- Memory            (Memory management. Arena, GC, etc.) 
        |-- Common            (Misc. supporting utilities) 
    |-- Runtime 
        |-- Base              (Depended on by the rest of the Runtime. 
                               e.g. ScriptContext, ThreadContext)
        |-- Types             (Type system) 
        |-- ByteCode          (Byte code definition, generator and serializer) 
        |-- Language          (Language implementation, e.g. interpreter loop 
                               and operators supporting running of JavaScript) 
        |-- Library           (JavaScript built in library implementation) 
        |-- Debug             (Debugger support) 
    |-- Parser                (JavaScript language and regex parser) 
    |-- Backend               (JIT native code generator) 
    |-- JSRT                  (JSRT API implementation)
|-- Bin 
    |-- ChakraCore            (Builds ChakraCore.dll) 
    |-- ch                    (Chakra Host, simple host running JavaScript from a file) 
    |-- rl                    (Unit test runner) 
|-- Build                     (Supporting build configuration and scripts) 
    |-- ... 
|-- Test                      (Unit tests) 
    |-- ...
</pre>