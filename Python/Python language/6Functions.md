
#### syntax:
A function is defined using the def keyword:
```
def my_function():  
  print("Hello from a function")

my_function()  # calling a function
```

#### Lambda Function:
A lambda function is a small anonymous function.
A lambda function can take any number of arguments, but can only have one expression.
Syntax:
```
lambda _arguments_ : _expression_
```
Example: Basic lambda function:
```
# Regular function
def add1(a, b):
    return a + b

# Equivalent lambda function
add2 = lambda a, b: a + b
print(add1(3, 5))  # Output: 8
print(add2(3, 5))  # Output: 8
```
##### Example of lambda function with data structure:
1.. Using with map:
```
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x ** 2, nums))
print(squared)  # Output: [1, 4, 9, 16]

```
2.. Using with filter:
```
nums = [1, 2, 3, 4, 5, 6]
even_nums = list(filter(lambda x: x % 2 == 0, nums))
print(even_nums)  # Output: [2, 4, 6]
```
3.. Using with reduce:
```
from functools import reduce

nums = [1, 2, 3, 4]
product = reduce(lambda x, y: x * y, nums)
print(product)  # Output: 24
```
#### Arguments and parameters:
```
def my_function(fname):  
  print(fname + " Refsnes")  
  
my_function("Emil")  
my_function("Tobias")  
my_function("Linus")
```


#### Arguments:
##### Default arguments:
A default argument is a parameter that assumes a default value if a value is not provided in the function call for that argument.
```
# default arguments
def myFun(x, y=50):
    print("x: ", x)
    print("y: ", y)
myFun(10)
```

##### Keyword Arguments
Sending arguments with the _key_ = _value_ syntax.
```
def my_function(child3, child2, child1):  
  print("The youngest child is " + child3)  
  
my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```

##### \*args Variable number of arguments:
If we do not know how many arguments that will be passed into your function, add a `*` before the parameter name in the function definition.

```
def fn(*args):
    print(args)
    print(args[len(args) - 1])

fn("suraj" , "akash" , "suravi" , "sukumar")
```
##### \*\*args : Variable length keyword arguments:

```
# Python program to illustrate
# *kwargs for variable number of keyword arguments


def myFun(**kwargs):
    for key, value in kwargs.items():
        print("%s == %s" % (key, value))


# Driver code
myFun(first='Geeks', mid='for', last='Geeks')
```


#### Return values:

syntax:
```
def function_name(parameters):
    # function logic
    return value
```

**Return multiple values:**
```
def calculate(a, b):
    return a + b, a - b, a * b

sum, diff, prod = calculate(10, 5)
print(sum, diff, prod)  # Output: 15 5 50

```

**Returning None**:
If there’s no `return` statement in a function or if `return` is used without any value, the function returns `None`.
```
def greet(name):
    print(f"Hello, {name}!")

result = greet("Alice")  # Prints: Hello, Alice!
print(result)  # Output: None
```

**Returning Data Structures**:
You can use the `return` statement to exit a function early, based on some condition.
```
def get_user_info():
    return {"name": "Alice", "age": 30}

user = get_user_info()
print(user["name"])  # Output: Alice

```

#### Yield:

