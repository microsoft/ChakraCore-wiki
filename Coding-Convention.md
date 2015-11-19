The following guidance was built by looking at [http://www.c-xx.com/ccc/ccc.php ](http://www.c-xx.com/ccc/ccc.php )and considering what exists in the CharkaCore codebase. ChakraCore does not consistently follow these patterns, nor is the team interested in making the entire codebase conform to them. 

Please,
* Do not send PRs for style changes.
* Do give priority to the current style of the project or file you're changing even if it diverges from the general guidelines.

And now, the ChakraCore coding guidelines:

* Class names - Pascal case. No "C" prefix or the like. We like: `FileName`
* Interfaces - prefix with "I" like `IFoo` as opposed to `FooInterface`
* Typedefs - apply class naming rules.
* Variable names - use Camel case. We like: `fileName`
* Use `m_` to prefix member variables. We like: `m_fileName`
* Group class data members together, please.
* It's OK to use prefix pointers with "p" but not required. Example: `void swap(int* pLeft, int* pRight)`
* Constants - Pascal case.
* Enumerations - Pascal case.
* Enumerators (the values within enumerations) - Pascal case.
* Namespaces - Pascal case.
* Functions - Pascal case.
* Preprocessor elements - ALL_CAPS
* Replace tabs with spaces. 
* Indentation is 4 spaces.
* Keep line length reasonable, but 80 character limit is not necessary.
* Braces - use this style:  
```
    Foo()  
    {  
        statement1;  
        statement2;  
    }
```

* Braces - include braces for single-statement blocks.
```
    if (condition)
    {
        a.single.statement;
    }
```
* Parenthesis and functions - please don't separate the opening paren from the function name.
```
    // We don't like this:
    FooBar
    (    x,
         y,
         z
    );
```

```
    // This is OK:
    FooBar(
        x,
        y,
        z
    ); 
```
* Do not put "else" or "catch" on the same line as a bracket. No: `} else`
* Do not put a space before ',' or ';' Do put a space after ','
* Do not use "table style" variable/member declarations. No:
```
    Int    x;
    Double y;
```
* Do not put spaces around brackets or parenthesis. No: `invocation( argument );`
* Do put a space after a control flow keyword like `for (int i; i < 10; i++)`
* Avoid using assignment as a value-producing operation. No: `if ((x = a[i]) >= '0' && x <= '9')`
* Chained assignment is OK. `x = y = z = 0;`
* Switch statements are to be formatted like so:
```
    switch (x)
    {
        case foo:
        {
            statement1;
            statement2;
            break;
        }
    }
```
* Braces around the case block is optional
* When declaring variables of pointer type group the asterisk with the variable, not the type being pointed to. Example `int *x;`
* Declare multiple variables on separate lines.
* Use `nullptr`
* Avoid `auto` except for long template names. The creation of a typedef for long template names is preferred.
* Do not use `const_cast<>()`
* Const: Avoid const objects and the declaration of const methods. We don't like the viral nature of const. Do use const on read-only global and static variables.
* Avoid the use of reference types.
* Avoid .inl files. Put implementations in the .cpp files. On Windows, PGO can make excellent inlining decisions.
* Do not use `__forceinline` unless there is a proven need. Even then think twice.
* For methods defined in headers, like accessors for example, you can implement them on the same line as the signature. 
