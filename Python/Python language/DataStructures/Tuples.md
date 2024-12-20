- Tuples are ordered collection of data items. 
- They store multiple items in a single variable. 
- Tuple items are separated by commas and enclosed within round brackets (). 
- Tuples are unchangeable meaning we can not alter them after creation.
- It allow duplicates.
- Tuple with a single element should have a comma after the element eg.
  tup = ("apple" , ) otherwise it will not consider as a tuple.


#### Syntax:
```
# Creating a tuple
empty_tuple = ()
single_element_tuple = (42,)  # Note the trailing comma for a single element
mixed_tuple = (1, "hello", 3.14)
nested_tuple = (1, (2, 3), [4, 5])
```

#### Operations
##### Accessing elements:
```
t = (10, 20, 30, 40, 50)
print(t[0])      # Output: 10
print(t[-1])     # Output: 50
```
##### slicing:
```
t = (10, 20, 30, 40, 50)
print(t[1:4])    # Output: (20, 30, 40)
print(t[:3])     # Output: (10, 20, 30)
```


| **Operation**       | **Description**                    | **Example**                | **Output**     |
| ------------------- | ---------------------------------- | -------------------------- | -------------- |
| `len(tuple)`        | Returns the number of elements.    | `len((1, 2, 3))`           | `3`            |
| `tuple[index]`      | Accesses the element at `index`.   | `t = (1, 2, 3); t[1]`      | `2`            |
| `tuple[start:stop]` | Slices the tuple.                  | `t = (1, 2, 3, 4); t[1:3]` | `(2, 3)`       |
| `x in tuple`        | Checks if `x` exists in the tuple. | `2 in (1, 2, 3)`           | `True`         |
| `tuple1 + tuple2`   | Concatenates two tuples.           | `(1, 2) + (3, 4)`          | `(1, 2, 3, 4)` |
| `tuple * n`         | Repeats the tuple `n` times.       | `(1, 2) * 2`               | `(1, 2, 1, 2)` |
##### Update tuple values:
Tuples are unchangeable, meaning that you cannot change, add, or remove items once the tuple is created.
Tricks to update tuples:
1. We can convert the tuple into a list, change the list, and convert the list back into a tuple.
```
x = ("apple", "banana", "cherry")  
y = list(x)  
y[1] = "kiwi"  
x = tuple(y)  
  
print(x)
```
2. **Add tuple to a tuple** :  We can add multiple tuples therefore we can add any numbers of items at the end of the tuple.
```
thistuple = ("apple", "banana", "cherry")  
y = ("orange",)  
thistuple += y  
  
print(thistuple)
```

##### Join tuples:
1. Concatenate:
```
tuple1 = ("a", "b" , "c")  
tuple2 = (1, 2, 3)  
  
tuple3 = tuple1 + tuple2  
print(tuple3)
```
2. Multiply
```
fruits = ("apple", "banana", "cherry")  
mytuple = fruits * 2  
  
print(mytuple)
```

##### unpacking tuples:
Unpacking means assigning values from the tuples to variables.
Syntax:
```
fruits = ("apple", "banana", "cherry")  
  
(green, yellow, red) = fruits  
  
print(green)  
print(yellow)  
print(red)
```
If the number of variables is less than the number of values, we can add an `*` to the variable name and the values will be assigned to the variable as a list:
```
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")  
  
(green, yellow, *red) = fruits  
  
print(green)  
print(yellow)  
print(red)
```
If the asterisk is added to another variable name than the last, Python will assign values to the variable until the number of values left matches the number of variables left.
```
fruits = ("apple", "mango", "papaya", "pineapple", "cherry")  
  
(green, *tropic, red) = fruits  
  
print(green)  
print(tropic)  
print(red)
```
#### Methods:
|**Method**|**Description**|**Example**|**Output**|
|---|---|---|---|
|`tuple.count(x)`|Returns the number of times `x` appears in the tuple.|`t = (1, 2, 2, 3); t.count(2)`|`2`|
|`tuple.index(x[, start[, end]])`|Returns the index of the first occurrence of `x` in the tuple. Raises a `ValueError` if `x` is not found.|`t = (1, 2, 3); t.index(2)`|`1`|
