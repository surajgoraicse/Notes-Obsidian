There are two types of loops in python:
1. while loop
2. for loop

==`The else statement will not execute if the loop is terminated by a break statement `==
#### While Loop:
syntax:
```
while expression:  
    statement(s)
```
Example:
```
count = 0
while (count < 3):
    count = count + 1
    print("Hello Geek")
```
##### Using else statement with While Loop in Python
The else clause is only executed when your while condition becomes false.
Syntax:
```
while condition:  
     # execute these statements  
else:  
     # execute these statements
```
Example : 
```
count =  1
while count <= 3:
    print("geek")
    count +=1
else:
    print("loop termintated")
```


#### For Loop
The `for` loop is used to iterate over sequences (like lists, tuples, strings, or ranges) and perform actions on each element.

Syntax:
```
for variable in sequence:
    # Code block to execute

```
Examples:
```
print("List Iteration")
l = ["geeks", "for", "geeks"]
for i in l:
    print(i)
    
print("\nTuple Iteration")
t = ("geeks", "for", "geeks")
for i in t:
    print(i)
    
print("\nString Iteration")
s = "Geeks"
for i in s:
    print(i)
    
print("\nDictionary Iteration")
d = dict({'x':123, 'y':354})
for i in d:
    print("%s  %d" % (i, d[i]))
    
print("\nSet Iteration")
set1 = {1, 2, 3, 4, 5, 6}
for i in set1:
    print(i),
```


##### Using `for` with `else`
Python allows an optional `else` block in a `for` loop. The `else` block executes after the loop finishes, but it does not execute if the loop is terminated prematurely with `break`.

```
for i in range(3):
    print(i)
else:
    print("Loop completed successfully.")

# output
0
1
2
Loop completed successfully.
```

```
for i in range(3):
    if i == 1:
        break
    print(i)
else:
    print("Loop completed successfully.")
# Output
0
```

##### Nested `for` Loops:
```
for i in range(3):
    for j in range(2):
        print(f"i={i}, j={j}")
```


#### break and continue Keywords:
1. break keyword exit the loop early:
```
for i in range(5):
    if i == 3:
        break
    print(i)
```
2. continue keyword skips a specified iteration:
```
for i in range(5):
    if i == 3:
        continue
    print(i)
```