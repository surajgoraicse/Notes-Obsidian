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
