The following guidance was built by looking at [http://www.c-xx.com/ccc/ccc.php ](http://www.c-xx.com/ccc/ccc.php )and considering what exists today in the CharkaCore codebase. ChakraCore does not consistently follow these patterns, nor are we interested in making the entire codebase conform to them. 

Please,
* DO NOT send PRs for style changes.
* DO give priority to the current style of the project or file you're changing even if it diverges from the general guidelines.

And now, the ChakraCore coding guidelines:

* Class names - Pascal case. No "C" prefix or the like. We like: "FileName"
* Interfaces - prefix with "I" like "IFoo" as opposed to "FooInterface"
* Typedefs - apply class naming rules.
* Variable names - use Camel case. We like: "fileName"
* Use "m_" to prefix member variables. We like: "m_fileName"
* Group class data members together, please.
* It's OK to use prefix pointers with "p" but not required. Example: "void swap(int* pLeft, int* pRight)"
* Constants - Pascal case.
* Enumerations - Pascal case.
* Enumerators (the values within enumerations) - Pascal case.
* Namespaces - Pascal case.
* Functions - Pascal case.
* Preprocessor elements - ALL_CAPS
* Replace tabs with spaces. 
* Indentation is 4 spaces.
* Keep line length reasonable, but 80 character limit is not necessary.
* Braces - use style A.  
`    Foo()  
        {  
            statement1;  
            statement2;  
        }`

* Braces - include braces for single-statement blocks.
`    if (condition)`
    `{`
        `a.single.statement;`
    `}`
* Parenthesis and functions - please don't separate the opening paren from the function name. We don't like this:
		FooBar
		(    x,
		     y,
		     z
		);
	This is OK:
		FooBar(
		    x,
		    y,
		    z
		); 
* Do not put "else" or "catch" on the same line as a bracket. No: "} else"
* No space before ',' or ';' Do put a space after. Except for '.'
* No "table style" variable/member declarations. No:
		Int    x;
		Double y;
* No spaces around brackets or parenthesis. No: "invocation( argument );"
* Add a space after a control flow keyword like "for (int i; i < 10; i++)"
* Avoid using assignment as a vaule-producing operation. No: "if ((x = a[i]) >= '0' && x <= '9')"
* Chained assignment is OK. "x = y = z = 0;"
* Switch statement formatting like this:
		Switch (x)
		{
			Case foo:
			{
				St1;
				St2;
			}
		};
* When declaring variables of pointer type group the asterisk with the variable, not the type being pointed to. Example "int *x;"
* Declare multiple variables on separate lines.
* Use "nullptr"
* Avoid "auto" except for long template names.
* No "const_cast<>()"
* Avoid const objects, and declaration of const methods. We don't really like the viral nature of const.
* Avoid the use of reference types.
* Avoid .inl files. Put implementations in the .cpp files. On Windows, PGO can make excellent inlining decisions.
* Do not use force_inline unless there is a proven need. Even then think twice.
* For methods defined in headers, like accessors for example, you can implement them on the same line as the signature. 
