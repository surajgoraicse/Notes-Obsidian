

##### Identifiers:
**Identifiers** in programming are names used to identify variables, functions, arrays, classes, etc.
Rules:
- Must begin with a letter (A-Z or a-z) or an underscore (`_`).
- Subsequent characters can include letters, digits (0-9), and underscores.
- Cannot be a reserved keyword.
- Case-Sensitive: Both lowercase and uppercase have different different meaning to the compiler.
- It must not contain white space.
#### What is Variable ?
- A **variable in C** is a memory location with some name that helps store some form of data and retrieves it when required. 


#### Types of Variables

There are three types of variables based on the scope of variables in C++.
- ***Local Variables***
- **Instance Variables***
- **Static Variables***

1. **Local Variables**: A variable defined within a block or method or constructor is called a local variable.   
    - These variables are created when entered into the block or the function is called and destroyed after exiting from the block or when the call returns from the function.
    - The scope of these variables exists only within the block in which the variable is declared. i.e. we can access this variable only within that block.
    - Initialization of local variables is not mandatory, but it is highly recommended to ensure they have a defined value before use.

2. **Instance Variables**: Instance variables are non-static variables and are declared in a class outside any method, constructor, or block.   
    - As instance variables are declared in a class, these variables are created when an object of the class is created and destroyed when the object is destroyed.
    - Unlike local variables, we may use access specifiers for instance variables. If we do not specify any access specifier then the default access specifier will be used.
    - Initialization of Instance Variable is not Mandatory.
    - Instance Variable can be accessed only by creating objects.

3. ***Static Variables***: Static variables are also known as Class variables.   
    - These variables are declared similarly as instance variables, the difference is that static variables are declared using the [static keyword](https://www.geeksforgeeks.org/static-keyword-cpp/) within a class outside any method constructor or block.
    - Unlike instance variables, we can only have one copy of a static variable per class irrespective of how many objects we create.
    - Static variables are created at the start of program execution and destroyed automatically when execution ends.
    - Initialization of Static Variable is not Mandatory. Its default value is 0
    - If we access the static variable like the Instance variable (through an object), the compiler will show the warning message and it won’t halt the program. The compiler will replace the object name with the class name automatically.
    - If we access the static variable without the class name, the Compiler will automatically append the class name.

#### Data Types

A **data type** specifies the type and size of the data that a variable can store. The memory allocated by the compiler to the variable is determined by the data type of the variable.

C++ have three types of data types:

1. Primary or Built-in or Fundamental data type
    
2. Derived data types
    
3. User-defined data types

##### Explanation
1. `Primitive Data Types`
    
    Primitive data types are built-in or predefined data types and can be used directly by the user to declare variables. example: int, char, float, bool, etc.
    
5. `Derived Data Types`
    
    Derived data types in C++ are data types that are derived from fundamental or built-in data types. They do not create entirely new data types but rather modify existing data types to create new ones with specific properties or structures.
    
6. `User defined Types`
    
    User-defined data types in C++ are data types that are defined by the programmer, rather than being built into the language.
    

|**`Primitive Data Types`**|**`Derived Data Types`**|**`User Defined`**|
|---|---|---|
|Int|Array|Structure|
|Float|Function|Union|
|Double|Pointer|Enum|
|char|Reference|Class|
|boolean||Typedef|
|void|||
#### Size of data types

| **Type**               | **Typical Bit Width** | **Typical Range**                           |
| ---------------------- | --------------------- | ------------------------------------------- |
| char                   | 1byte                 | -127 to 127 or 0 to 255                     |
| unsigned char          | 1byte                 | 0 to 255                                    |
| signed char            | 1byte                 | -127 to 127                                 |
| int                    | 4bytes                | -2147483648 to 2147483647                   |
| unsigned int           | 4bytes                | 0 to 4294967295                             |
| signed int             | 4bytes                | -2147483648 to 2147483647                   |
| short int              | 2bytes                | -32768 to 32767                             |
| unsigned short int     | 2bytes                | 0 to 65,535                                 |
| signed short int       | 2bytes                | -32768 to 32767                             |
| long int               | 8bytes                | -9223372036854775808 to 9223372036854775807 |
| signed long int        | 8bytes                | same as long int                            |
| unsigned long int      | 8bytes                | 0 to 18446744073709551615                   |
| long long int          | 8bytes                | -(2^63) to (2^63)-1                         |
| unsigned long long int | 8bytes                | 0 to 18,446,744,073,709,551,615             |
| float                  | 4bytes                |                                             |
| double                 | 8bytes                |                                             |
| long double            | 12bytes               |                                             |
| wchar_t                | 2 or 4 bytes          | 1 wide character                            |

#### Type Conversion:
##### Implicit Type Conversion: 
- Done by the compiler on its own, without any external trigger from the user.
- Generally takes place when in an expression more than one data type is present. In such condition type conversion (type promotion) takes place to avoid lose of data.
- All the data types of the variables are upgraded to the data type of the variable with largest data type.
```
bool -> char -> short int -> int -> 

unsigned int -> long -> unsigned -> 

long long -> float -> double -> long double
```

##### Explicit Type Conversion:
1. **Converting by assignment*** : 
	`int ans = (int)(a+b);`
2. ***Cast operator*** : 
   1. static_cast:
   2. dynamic_cast
   3. const_cast
   4. reinterpret_cast

###### [Cast Operator](https://www.geeksforgeeks.org/casting-operators-in-cpp/?ref=lbp): 

**static_cast*** : Used for standard type conversions (e.g., numeric conversions, pointers, etc.). It performs compile-time checking, ensuring type safety.
```
double a = 5.67;
int b = static_cast<int>(a); // Converts 'double' to 'int'
std::cout << b; // Output: 5
```

dynamic_cast : 

#### Escape Sequence
Escape sequences in C++ are characters or sequences of characters that can be used inside a string literal to represent some special characters. They are prefixed with a backslash \ and are used to represent characters such as new line, carriage return, etc. that cannot be represented normally.

| Escape Sequence | Name               | Description                                                                         |
| --------------- | ------------------ | ----------------------------------------------------------------------------------- |
| \\              | Backslash          | Inserts a backslash character.                                                      |
| \'              | Single quote       | Displays a single quotation mark.                                                   |
| \"              | Double quote       | Displays double quotation marks.                                                    |
| \?              | Question mark      | Displays a question mark.                                                           |
| \a              | Alert (bell)       | Generates a bell sound in the C++ program.                                          |
| \b              | Backspace          | Moves the cursor one place backward.                                                |
| \f              | Form feed          | Moves the cursor to the start of the next logical page.                             |
| \n              | New line           | Moves the cursor to the start of the next line.                                     |
| \r              | Carriage return    | Moves the cursor to the start of the current line.                                  |
| \t              | Horizontal tab     | Inserts some whitespace to the left of the cursor and moves the cursor accordingly. |
| \v              | Vertical tab       | Inserts vertical space.                                                             |
| \0              | Null character     | Represents the NULL character.                                                      |
| \ooo            | Octal number       | Represents an octal number.                                                         |
| \xhh            | Hexadecimal number | Represents a hexadecimal number.                                                    |

#### Variable Scope 
The scope of a variable is the is the region of the program where the variable is accessible.


##### In C++, there are mainly two types of variable scopes:
1. Local Scope
2. Global Scope


##### Explanation: 
1. Local Scope : It is defined inside a block (curly braces ) and has scope within that block only.
2. Global Scope : Global scope refers to the region **outside*** any function or a block. The variables declared here are accessible throughout the entire program and are called Global Variables.

##### Variable Shadowing
- If two variables with same name are defined in different scopes, the compiler allows it and does not show error.
- Whenever there is a local variable defined with same name as that of a global variable, the ***precedence is given to the local variable.*** This is called variable shadowing.
**Access Global Variable in Variable Shadowing :**
Scope resolution operator( :: ) is used to access global variable in variable shadowing. 
```
#include<iostream>
using namespace std;
int value = 3434;
int main() {
    int value = 0;
    cout << ::value;  // output: 3434
}
```


#### Other types of Scopes in C++

Apart from the primary classification of the scopes as global and local, there are few other specialized variations of these scopes that divides the declared variable based on its accessibility and visibility. Following are some common variations of variable scopes in C++.

- Instance Scope
- Static Member Scope
- Namespace Scope

##### Explanation:
###### Instance Scope:
In C++, instance scope refers to the region inside a class but outside any member function of the class. The variable declared here are called instance variables and are accessible to whole class. They can be accessed by the objects of the class.
###### Static Member Scope:
The static scope applies to variables and functions declared with the static keyword within the class. These variables are shared across all instances of a class and can be accessed using the class name without creating the instance.

###### Namespace Scope:
A namespace in C++ is a container that allows users to create a separate scope where the given variables are defined. It is used to avoid name conflicts and group related code together. These variables can be then accessed using their namespace name and scope resolution operator.


