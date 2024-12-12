
#### Preprocessor and Preprocessor Directives

##### `What is preprocessor ?`

The **preprocessor** in C++ is used for processing the code before it is compiled by the compiler. It does many tasks such as including files, conditional compilation, using macros, etc. The preprocessor also allows the developers to select which portions of code should be included or excluded.

##### `What is preprocessor Directives ?`

In C++, the preprocessor directives are special commands that are used to instruct the preprocessor. It begins with a **‘#’** symbol and tells the preprocessor to the modify source code before compilation.

Some `example` of preprocessors are : **#include , #define , #undef etc.**


#### namespace

- Namespace provide the space where we can define or declare identifier i.e. variable, method, classes.
- Using namespace, we can define the space or context in which identifiers are defined i.e. variable, method, classes. In essence, a namespace defines a scope.

**`Example**:`

- You might be writing some code that has a function called xyz() and there is another library available which is also having same function xyz(). Now the compiler has no way of knowing which version of xyz() function you are referring to within your code.
- A namespace is designed to overcome this difficulty and is used as additional information to differentiate similar functions, classes, variables etc. with the same name available in different libraries.
- The best example of namespace scope is the C++ `standard library` (std) where all the classes, methods and templates are declared. Hence while writing a C++ program we usually include the directive using namespace std;

#### Header Files:
Header files are those files that store predefined functions. It contains definitions of functions that you can include or import using a preprocessor directive `#include`.

**header files** are used to store the structure of code, such as functions, classes, constants, and macros, that can be included in multiple source files. 

They allow for the separation of implementation and declaration, making code more modular, reusable, and maintainable.

##### Key Features of Header files:
**Declarations**:
- Header files contain declarations (not definitions) of functions, variables, and classes.
- The actual implementation (definitions) is typically placed in `.cpp` source files.

**Inclusion**:
- Header files are included in other files using the `#include` directive.
```
#include <iostream> // Standard library header file
#include "myHeader.h" // User-defined header file
```

**Code Reusability**:
- By defining common functionality in a header file, it can be reused across multiple `.cpp` files.

**Preprocessor Directives**:
- Guards prevent multiple inclusions of the same header file, which can cause errors.
```
#ifndef HEADER_FILE
#define HEADER_FILE

// Declarations here

#endif
```

#### How Header Files Work:
1. **Structure**:
    - A header file (e.g., `myHeader.h`) typically contains:
        - Function prototypes.
        - Class declarations.
        - Constants and macros.
        - Template definitions.
```
file: myHeader.h
// Function to find the sum of two
// numbers passed
int sumOfTwoNumbers(int a, int b) { 
	return (a + b); 
};
```

2. **Including in Main File**:
    - The header file is included in the main source file:
```
// myHeader.cpp
#include "myHeader.h"
#include <iostream>

int main(){
	int sum = sumOfTwoNumbers(4,5);
	cout<<sum<<endl;
	return 0;
}
```

##### There are two types of header files:
1. **Standard Library Header Files**:
    - These are provided by the C++ standard library and do not require implementation by the user.
    - Examples:
        - `<iostream>`: For input/output operations.
        - `<vector>`: For the `std::vector` container.
        - `<cmath>`: For mathematical functions.
2. **User-Defined Header Files**:
    - Created by the programmer to organize custom code.
    - Typically use the `.h` or `.hpp` extension.

