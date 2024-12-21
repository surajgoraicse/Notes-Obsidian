#### map():
The `map()` function executes a specified function for each item in an iterable. The item is sent to the function as a parameter.
The map has to be converted back into iterable object for readibility.
##### Syntax:
`map(function , iterable object)`
`list(map(function , iterable object))`


##### Example:
```
# Find Square of a list
def square(n):
    return n*n

arr = [1,2,3,4,5,6,7]
result = list(map(square , arr))
print(result)

```