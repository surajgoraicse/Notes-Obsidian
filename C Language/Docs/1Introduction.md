#### What is C ?
C is a general-purpose, procedural, high-level programming language used in the development of computer software and applications, system programming, games, and more.
- C language was developed by Dennis Ritchie at the Bell labs in 1972.
- It was developed for programming UNIX operating System.

##### What is general-purpose programming language ?
- A **general-purpose programming language** is a type of programming language designed to solve a wide range of problems across different domains, such as web development, system programming, data analysis, and more. 
- These languages are not specialized for any specific task but are versatile and flexible enough for various applications.

##### What is procedural programming language ?
- A procedural programming language is a type of programming language that uses a structured approach to solve problems by dividing them into reusable blocks called procedures or functions.


##### What is a low level programming language ?
- A low-level programming language is a programming language that runs closer to a computer's hardware and machine code.
- It allows programmers to have direct control over the computer's resources and hardware.
##### What is a high level programming language ?
A high-level programming language is a type of programming language that is designed to be easy for humans to read and write. It abstracts away the details of the computer's hardware and provides a more user-friendly syntax, making it easier to develop software. Examples include Python, Java, and JavaScript.
##### What is a mid level programming language ?
A mid-level programming language is a language that combines features of both high-level and low-level languages. It provides some abstraction from the hardware while still allowing direct access to memory and hardware resources. Mid-level languages offer a balance between ease of use and control over system performance. Examples include **C** and **C++**.


#### Components of a C Program:
##### Header Files:
- A header file is a file with extension .h which contains C function declarations and macro definitions.
- Header files are included in C programs using the `#include` directive. Common examples of header files are `stdio.h`, `stdlib.h`, and `string.h`.
##### Main Method Declaration:
- It is the entry point of a C program and the execution typically begins with the first line of the main(). 
- The empty brackets indicate that the main doesn’t take any parameter.
##### Body of Main Method
- Set of code defined in the main function.
##### Return Statement
- The return statement refers to the return values from a function.
- The returned value may be used by an operating system to know the termination status of your program. The value 0 typically means successful termination.
#### Application of C
- Operating systems: C is widely used for developing operating systems such as Unix, Linux, and Windows.
- Embedded systems: C is a popular language for developing embedded systems such as microcontrollers, microprocessors, and other electronic devices.
- **System software****: C is used for developing system software such as device drivers, compilers, and assemblers.
- **Networking****: C is widely used for developing networking applications such as web servers, network protocols, and network drivers.
- **Database systems****: C is used for developing database systems such as Oracle, MySQL, and PostgreSQL.
- **Gaming****: C is often used for developing computer games due to its ability to handle low-level hardware interactions.
- **Artificial Intelligence****: C is used for developing artificial intelligence and machine learning applications such as neural networks and deep learning algorithms.
- **Scientific applications****: C is used for developing scientific applications such as simulation software and numerical analysis tools.
- ***Financial applications****: C is used for developing financial applications such as stock market analysis and trading systems.

#### Compilation and Interpretation:

##### What is a compiler ?
- A **compiler** is a program that translates source code written in a high-level programming language (like C, C++, or Java) into machine code or an intermediate form (such as bytecode) that a computer's processor can execute. 
- The compiler processes the entire code, checks for errors, and produces an executable file that can run on the target system.
- Some examples of compilers are GCC, turbo c, clang etc.
##### Does a low level programming language also need a compiler ?
Yes, **low-level programming languages** also require compilers or assemblers.
Low-level programming languages typically refer to **assembly language** and **machine language**:
- **Assembly Language**:
    - **Needs an Assembler**: Assembly language is a symbolic representation of machine code, and it needs an **assembler** to convert the assembly code into machine code (binary code) that can be executed by a computer's processor.
- **Machine Language**:
    - **Direct Execution**: Machine language is already in the form of binary code, which the computer's CPU can execute directly. Therefore, there is no need for a compiler or an assembler for machine language since it's already in the format the processor understands.

##### Difference between compiled language and interpreted language:
| Compiled Language                                                                                                                             | Interpreted Language                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| The entire source code is translated into machine code (or an intermediate form) by a **compiler** before execution.                          | The source code is translated **line-by-line** or **statement-by-statement** into machine code by an **interpreter** during execution. |
| The result is an **executable file** that can be run directly by the computer without needing the original source code or the compiler.       | No separate executable file is generated. The interpreter must be present to run the code.                                             |
| Generally **faster** execution because the entire code is translated beforehand into machine code, which can be directly executed by the CPU. | **Slower** execution because the interpreter translates and executes the code on the fly, one line at a time.                          |
| Errors are detected **before execution**.                                                                                                     | Errors are detected **during execution**.                                                                                              |
| The compiled executable is platform-specific. To run on a different platform, you need to recompile the code for that platform.               | The same source code can run on any platform with the appropriate interpreter installed, making it more **platform-independent**.      |
| **Examples**: C, C++, Rust.                                                                                                                   | **Examples**: Python, JavaScript, Ruby.                                                                                                |

#### What goes inside the compilation process?
A compiler converts a C program into an executable. There are four phases for a C program to become an executable: 

1. ***Pre-processing***
2. ***Compilation***
3. ***Assembly***
4. ***Linking***
##### Pre-processing
This is the first phase through which source code is passed. This phase includes:

- Removal of Comments
- Expansion of Macros
- Expansion of the included files.
- Conditional compilation

The preprocessed output is stored in the ****filename.i****.

##### Compiling:
The next step is to compile filename.i and produce an; intermediate compiled output file **filename.s**. This file is in assembly-level instructions.

##### Assembling
In this phase the filename.s is converted into machine code by the assembler and stored with filename.o extension . This file contains machine-level instructions.

##### Linking
This is the final phase in which all the linking of function calls with their definitions is done. Linker knows where all these functions are implemented. Linker does some extra work also, it adds some extra code to our program which is required when the program starts and ends.


#### Comments:
- **Comments** in programming are non-executable lines of text that are included in the source code for the purpose of explaining and documenting the code. 
- Comments are ignored by the compiler or interpreter during execution but help developers understand the code, its logic, or its purpose and increases readability. 
##### Types of comments:
1. Single Line comment:  ` // this is a comment `
2. Multiline comment: `/*  this is a multi-line comment */`

#### Tokens:
A token in C can be defined as the smallest individual element of the C programming language that is meaningful to the compiler.
##### Types of Tokens in C:
There are six types of tokens:
1. ***Keywords***
2. **Identifiers***
3. ***Constants***
4. **Strings***
5. ***Special Symbols***
6. ***Operators***

##### Keywords:
- The keywords are pre-defined or reserved words in a programming language.
- These are part of the syntax and cannot be used as identifiers in the program.
- There are 32 reserved keyword in C language.

##### Identifiers:
**Identifiers** in programming are names used to identify variables, functions, arrays, classes, etc.
Rules:
- Must begin with a letter (A-Z or a-z) or an underscore (`_`).
- Subsequent characters can include letters, digits (0-9), and underscores.
- Cannot be a reserved keyword.
- Case-Sensitive: Both lowercase and uppercase have different different meaning to the compiler.
- It must not contain white space.

##### Constants:
- The constants refer to the variables with fixed values.
- Constants should be initialized during declaration.

##### Strings:
In **C programming**, a **string** is a sequence of characters stored in an array of characters. It is used to represent text and is typically terminated by a special null character (`'\0'`), which indicates the end of the string.

##### Special Symbols
The following special symbols are used in C having some special meaning and thus, cannot be used for some other purpose. Some of these are listed below:
- **Brackets[]:** 
- **Parentheses():** 
- **Braces{}:** 
- **Comma (, ):***
- **Colon(:):** 

#####  Operators:
Operators symbols that trigger an action when applied to C variables and other objects.

