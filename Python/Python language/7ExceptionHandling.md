- Error in Python can be of two types i.e. Syntax errors and Exceptions.
- Errors are problems in a program due to which the program will stop the execution. On the other hand, exceptions are raised when some internal events occur which change the normal flow of the program.

#### Exception Handling:
When an error occurs, or exception as we call it, Python will normally stop and generate an error message.
These exceptions can be handled using the `try` statement:

##### Syntax:
```
try:
    # Code that might raise an exception
    risky_operation()
except ExceptionType:
    # Code to handle the exception
    handle_error()
else:
    # Code to execute if no exception occurs
    success_code()
finally:
    # Code that always executes, regardless of exceptions
    cleanup_code()
```

##### Components of Exception handling:
###### 1. `try` Block:
The `try` block contains the code that might raise an exception.

###### 2. `except` Block:
The `except` block handles the exception. You can also specify the type of exception to catch.
###### 3. `else` Block:
The `else` block is executed only if no exceptions occur in the `try` block.

###### 4. `finally` Block:
The `finally` block always executes, whether an exception occurs or not. It's often used for cleanup.
##### Handling Multiple Exceptions:

You can catch multiple exceptions using multiple `except` blocks or a single block with a tuple.
```
try:
    x = int("hello")
except ValueError:
    print("Value error occurred!")
except TypeError:
    print("Type error occurred!")
```
Using tuples:
```
try:
    x = 1 / 0
except (ValueError, ZeroDivisionError):
    print("An error occurred!")
```

#### Example:
```
try:
    number = int(input("Enter a number: "))
    result = 100 / number
except ValueError:
    print("Invalid input! Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero!")
else:
    print(f"Result is: {result}")
finally:
    print("Execution completed.")
```
Output:
```
# Input: `abc`
Invalid input! Please enter a valid number.
Execution completed.

#Input: `0`
Cannot divide by zero!
Execution completed.

#Input: `10`
Result is: 10.0
Execution completed.
```
#### Custom Exceptions
We can create your own exceptions by subclassing the `Exception` class.
```
class NegativeValueError(Exception):
    pass

def check_positive(number):
    if number < 0:
        raise NegativeValueError("Negative value provided!")

try:
    check_positive(-10)
except NegativeValueError as e:
    print(e)
```



#### Types of exceptions:

| **Exception Name**    | **Description**                                                                                                          | **Example Code**                          | **Resolution**                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------- | -------------------------------------------------------------------------------- |
| **SyntaxError**       | Raised when the interpreter encounters a syntax error in the code, such as a missing colon or an unbalanced parenthesis. | `if True print("Hello")`                  | Add missing syntax (e.g., a colon: `if True: print("Hello")`).                   |
| **TypeError**         | Raised when an operation is applied to an object of the wrong type.                                                      | `3 + "hello"`                             | Ensure operands are compatible (e.g., convert `3` to a string: `"3" + "hello"`). |
| **NameError**         | Raised when a variable or function name is not found in the current scope.                                               | `print(x)` (if `x` is undefined)          | Define or import the variable or function before using it.                       |
| **IndexError**        | Raised when an index is out of range for a list or tuple.                                                                | `lst = [1, 2]; print(lst[5])`             | Use valid indices (`print(lst[-1])` for the last element).                       |
| **KeyError**          | Raised when a key is not found in a dictionary.                                                                          | `my_dict = {"a": 1}; print(my_dict["b"])` | Check key existence using `in` (`if "b" in my_dict`).                            |
| **ValueError**        | Raised when a function or method is called with invalid input.                                                           | `int("hello")`                            | Validate inputs before calling the function.                                     |
| **AttributeError**    | Raised when an attribute or method is not found on an object.                                                            | `"hello".append("world")`                 | Check if the object supports the attribute (`dir(object)` can help).             |
| **IOError**           | Raised when an I/O operation (e.g., file read/write) fails due to input/output issues.                                   | `open("nonexistent.txt")`                 | Use `try-except` or check file existence (`os.path.exists("file")`).             |
| **ZeroDivisionError** | Raised when attempting to divide a number by zero.                                                                       | `10 / 0`                                  | Ensure the divisor is not zero (`if divisor != 0`).                              |
| **ImportError**       | Raised when an import statement fails to find or load a module.                                                          | `import nonexistentmodule`                | Verify module installation (`pip install module_name`).                          |
|                       |                                                                                                                          |                                           |                                                                                  |
