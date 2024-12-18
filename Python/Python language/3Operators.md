### Types of Operators in Python

1. Arithmetic Operators
2. Comparison Operators
3. Logical Operators
4. Bitwise Operators
5. Assignment Operators
6. Identity Operators and Membership Operators

#### Arithmetic Operators
| Operator | Description                                                                    | Syntax |
| -------- | ------------------------------------------------------------------------------ | ------ |
| +        | Addition: adds two operands                                                    | x + y  |
| –        | Subtraction: subtracts two operands                                            | x – y  |
| *        | Multiplication: multiplies two operands                                        | x * y  |
| /        | Division (float): divides the first operand by the second (returns float)      | x / y  |
| //       | Division (floor): divides the first operand by the second (return int)         | x // y |
| %        | Modulus: returns the remainder when the first operand is divided by the second | x % y  |
| **       | Power: Returns first raised to power second                                    | x ** y |
##### Float division
The quotient returned by this operator is always a float number, no matter if two numbers are integers.
```
print(5/5)  // 1.0
print(10/2) // 5.0
print(-10/2)  // -5.0
print(20.0/2) // 10.0
```

##### Integer division( Floor division)****

The quotient returned by this operator is dependent on the argument being passed. If any of the numbers is float, it returns output in float. It is also known as Floor division because, if any number is negative, then the output will be floored. For example:
```
print(10//3) # 3
print (-5//2) # -3
print (5.0//2) # 2.0
print (-5.0//2) #-3.0
```

##### The precedence of Arithmetic Operators in Python is as follows:

1. P – Parentheses
2. E – Exponentiation
3. M – Multiplication (Multiplication and division have the same precedence)
4. D – Division
5. A – Addition (Addition and subtraction have the same precedence)
6. S – Subtraction
#### Comparison Operators

Comparison operator returns either True or False.

|Operator|Description|Syntax|
|---|---|---|
|>|Greater than: True if the left operand is greater than the right|x > y|
|<|Less than: True if the left operand is less than the right|x < y|
|==|Equal to: True if both operands are equal|x == y|
|!=|Not equal to – True if operands are not equal|x != y|
|>=|Greater than or equal to True if the left operand is greater than or equal to the right|x >= y|
|<=|Less than or equal to True if the left operand is less than or equal to the right|x <= y|

#### Logical Operators

|Operator|Description|Syntax|
|---|---|---|
|and|Logical AND: True if both the operands are true|x and y|
|or|Logical OR: True if either of the operands is true|x or y|
|not|Logical NOT: True if the operand is false|not x|
##### Precedence of Logical Operators in Python
1. Logical not
2. logical and
3. logical or

##### Example:
```
a = True
b = False
print(a and b)  # False
print(a or b)   # True
print(not a)    # False
```


#### Bitwise Operator

|Operator|Description|Syntax|
|---|---|---|
|&|Bitwise AND|x & y|
|\||Bitwise OR|x \| y|
|~|Bitwise NOT|~x|
|^|Bitwise XOR|x ^ y|
|>>|Bitwise right shift|x>>|
|<<|Bitwise left shift|x<<|
##### The precedence of Bitwise Operators in Python is as follows:

1. Bitwise NOT
2. Bitwise Shift
3. Bitwise AND
4. Bitwise XOR
5. Bitwise OR