# OOP-Detector (C++ source scanner)

Pequeño analizador léxico + parser de **descenso recursivo** escrito en C++
que identifica rasgos de Programación Orientada a Objetos en archivos C++.

---
g++ -std=c++17 -g -o main tokenizer/token.cpp Parser.cpp
./main <"File Name">


| **Token**              | **Regex**                                  | **Description**                         | **Justification**                                     |
| ---------------------- | ------------------------------------------ | --------------------------------------- | ----------------------------------------------------- |
| `CLASS_KW`             | `class`                                    | Class keyword                           | Identifies the beginning of a class declaration.      |
| `IDENTIFIER`           | `[a-zA-Z_][a-zA-Z0-9_]*`                   | Names for variables, functions, classes | Used to label entities defined by the user.           |
| `TYPE`                 | e.g., `int`, `float`, `char`, `void`, etc. | Data types                              | Represents built-in and user-defined types.           |
| `ESPECIFICADOR_ACCESO` | `public`, `private`, `protected`           | Access modifiers                        | Controls visibility of class members.                 |
| `ABRE_LLAVE`           | `{`                                        | Block opening                           | Marks the start of class/function/code blocks.        |
| `CIERRA_LLAVE`         | `}`                                        | Block closing                           | Marks the end of class/function/code blocks.          |
| `ABRE_PAR`             | `\(`                                       | Open parenthesis                        | Used in function calls and parameter lists.           |
| `CIERRA_PAR`           | `\)`                                       | Close parenthesis                       | Used in function calls and parameter lists.           |
| `DOS_PUNTOS`           | `:`                                        | Colon                                   | Used for inheritance or initializer lists.            |
| `COMA`                 | `,`                                        | Comma separator                         | Separates parameters or arguments.                    |
| `IGUAL`                | `=`                                        | Assignment operator                     | Assigns values in declarations and expressions.       |
| `NEW`                  | `new`                                      | Allocation keyword                      | Used to dynamically allocate memory.                  |
| `EXTRA`                | `.` or `::` or other C++ operators         | Miscellaneous operators                 | Captures common operators not specifically tokenized. |
| `NUMBER`               | `[0-9]+` or `[0-9]*\.[0-9]+`               | Numeric literals                        | Used in expressions and return values.                |
| `ARROW`                | `->`                                       | Member access through pointer           | Used in method calls via pointers.                    |
| `DELETE`               | `delete`                                   | Deallocation keyword                    | Used to free dynamically allocated memory.            |
| `RETURN_KW`            | `return`                                   | Return keyword                          | Used in functions to return a value.                  |
| `SQUIGLY`              | `~`                                        | Tilde for destructor naming             | Identifies destructor declarations.                   |
| `END`                  | `;`                                        | Statement terminator                    | Denotes end of a declaration or instruction.          |
| `EPSILON`              | —                                          | Empty production                        | Used in grammar to indicate optional constructs.      |