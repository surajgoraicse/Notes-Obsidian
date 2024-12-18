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
