# PLM (Programming Language of the Moment) Parser and Interpreter

This project implements a parser and interpreter for PLM, a simple programming language designed to compute non-negative integers. The project consists of a lexer and parser that validate PLM programs and an interpreter that evaluates them.

## Overview
PLM allows users to define functions and includes basic arithmetic operations. The project focuses on parsing function definitions, handling comments, and executing the main function while checking for errors.

## How It Works
### Parser Implementation
The parser is designed to recognize valid PLM programs according to specific syntax rules:

* Function Definitions: Each function must follow the format:
```java
DEF function_name parameter_name { function_body } ;
```
The function body must be an arithmetic expression without spaces, and function names must be uppercase letters while parameter names must be lowercase letters.

* Comments: Comments are defined using `/* comment */` syntax and can contain any ASCII characters.

* Validation: The parser checks for various conditions:
  * The presence of a MAIN function.
  * Valid function names and parameters.
  * Proper placement of braces and semicolons.
  * Absence of whitespace within function bodies.

### Interpreter Implementation
The interpreter evaluates PLM programs by executing the MAIN function and resolving function calls:

* Function Calls: When a function is called, the arguments are evaluated first, and their values are substituted into the function body.
* Error Handling: If the program leads to circular dependencies or does not conform to the PLM rules, appropriate error messages are generated.

### Input/Output Specifications
* Standard Input: The parser reads from `System.in`.
* Output: Valid programs output `PASS` followed by the evaluation result or `LOOP` for infinite loops. Invalid programs output `FAIL` with an error message to `System.err`, including the line number of the error.
