ChatGpt : Roast me on basis of previous prompt.
#### Comment
`Inline comment : ` # this is a comment 
`Multi-line comment` :  """ this is a multi-line comment """


#### What is Python?
- Python is a dynamically typed, General Purpose Programming Language that supports an object-oriented programming approach as well as a functional programming approach.
- Python is also an interpreted and high-level programming language.
- Python is an open-source programming language.
- It is possible to integrate other programming languages within python.
- It was created by Guido Van Rossum in 1989.


#### What is Variable ?
- A **variable in python** is a memory location with some name that helps store some form of data and retrieves it when required. 

##### Rules for defining variables : 
- Variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable name must start with a letter or the underscore character.
- Variables are case sensitive.
- Variable name cannot start with a number.
##### Dynamic Typing
Python variables are dynamically typed, meaning the same variable can hold different types of values during execution.

#####  Multiple Assignments
```
a = b = c = 100
print(a, b, c)
```
Assigning Different Values
```
x, y, z = 1, 2.5, "Python"
print(x, y, z)
```



#### Scope

##### Local Variables:
Variables defined inside a function are local to that function.
```
def f():
    a = "I am local"
    print(a)

f()
# print(a)  # This would raise an error since 'local_var' is not accessible outside the function
```

##### Global Variables:
Variables defined outside any function are global and can be accessed inside functions using the global` keyword.
```
a = "I am global"

def f():
    global a
    a = "Modified globally"
    print(a) // Modified globally

f()
print(a) // Modified globally
```

#### Data Types
A **data type** specifies the type and size of the data that a variable can store. The memory allocated to the variable is determined by the data type of the variable.

|   |   |
|---|---|
|Text Type:|`str`|
|Numeric Types:|`int`, `float`, `complex`|
|Sequence Types:|`list`, `tuple`, `range`|
|Mapping Type:|`dict`|
|Set Types:|`set`, `frozenset`|
|Boolean Type:|`bool`|
|Binary Types:|`bytes`, `bytearray`, `memoryview`|
|None Type:|`NoneType`|

##### Getting the Type of Variable
we can determine the type of a variable using the type() function.
```
# Define variables with different data types
n = 42
f = 3.14
s = "Hello, World!"
li = [1, 2, 3]
d = {'key': 'value'}
bool = True

# Get and print the type of each variable
print(type(n))   
print(type(f)) 
print(type(s))   
print(type(li))     
print(type(d))     
print(type(bool))
```


##### Example:
| Example                                      | Data Type  |
| -------------------------------------------- | :--------: |
| x = "Hello World"                            |    str     |
| x = 20                                       |    int     |
| x = 20.5                                     |   float    |
| x = 1j                                       |  complex   |
| x = ["apple", "banana", "cherry"]            |    list    |
| x = ("apple", "banana", "cherry")            |   tuple    |
| x = range(6)                                 |   range    |
| x = {"name" : "John", "age" : 36}            |    dict    |
| x = {"apple", "banana", "cherry"}            |    set     |
| x = frozenset({"apple", "banana", "cherry"}) | frozenset  |
| x = True                                     |    bool    |
| x = b"Hello"                                 |   bytes    |
| x = bytearray(5)                             | bytearray  |
| x = memoryview(bytes(5))                     | memoryview |
| x = None                                     |  NoneType  |

##### Setting the Specific Data Type:

| Example                                      | Data Type  |
| -------------------------------------------- | :--------: |
| x = str("Hello World")                       |    str     |
| x = int(20)                                  |    int     |
| x = float(20.5)                              |   float    |
| x = complex(1j)                              |  complex   |
| x = list(("apple", "banana", "cherry"))      |    list    |
| x = tuple(("apple", "banana", "cherry"))     |   tuple    |
| x = range(6)                                 |   range    |
| x = dict(name="John", age=36)                |    dict    |
| x = set(("apple", "banana", "cherry"))       |    set     |
| x = frozenset(("apple", "banana", "cherry")) | frozenset  |
| x = bool(5)                                  |    bool    |
| x = bytes(5)                                 |   bytes    |
| x = bytearray(5)                             | bytearray  |
| x = memoryview(bytes(5))                     | memoryview |

##### Type Casting 
**Casting** refers to converting one data type to another.
Example:
```
n = int(3.345) // 3
m = bool("suraj) // True
o = float(34) // 34.0
 
```

##### Delete a Variable Using `del` Keyword
We can remove a variable from the namespace using the del keyword. This effectively deletes the variable and frees up the memory it was using.
```
# Assigning value to variable
x = 10
print(x) 

# Removing the variable using del
del x

# Trying to print x after deletion will raise an error
# print(x)  # Uncommenting this line will raise NameError: name 'x' is not defined
```





#### User input:
- The `input()` function reads a line of text entered by the user from the standard input (keyboard).
- It always returns the input as a **string**.

Syntax:
```
name = input("What is your name? ")
print("Hello, " + name + "!")
```

##### Handling Multiple Inputs

1. Using `split()` : You can take multiple inputs in one line by using `split()` to break the input string into parts.
```
x, y = input("Enter two numbers separated by space: ").split()
x = int(x)
y = int(y)
print("Sum:", x + y)    # 15

```

2. **Using a Loop**:
   For unknown or variable numbers of inputs, you can use a loop.
```
numbers = input("Enter numbers separated by spaces: ").split()
numbers = [int(num) for num in numbers]  # Convert each input to an integer
print("Numbers:", numbers)
```


##### Error handling:
To handle invalid inputs gracefully, you can use a `try-except` block.
```
try:
    age = int(input("Enter your age: "))
    print("You entered:", age)
except ValueError:
    print("Invalid input! Please enter a number.")

```

##### Advance Technique
1.. Input with a default value:
```
name = input("Enter your name (default: Guest): ") or "Guest"
print("Welcome,", name)
```
