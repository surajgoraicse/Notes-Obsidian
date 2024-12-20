- A **list** in Python is a collection of ordered, mutable (changeable), and potentially heterogeneous (containing items of different types) elements.
- They are created using square brackets.
- **Ordered**: The items in a list have a defined order, meaning the order of elements is preserved. The first item in the list will always remain the first item unless explicitly changed.



#### Syntax:
```
my_list = [1, 2, 3, 4, 5]
print(my_list)
```
Accessing elements: 
- It also accept negative indexing where -1 represents the last element.
```
print(my_list[0])  # Output: 1 (first element)
print(my_list[-1])  # Output: 5 (last element using negative index)
```
Modifying elements:
```
my_list[2] = 10  # Changes the third element from 3 to 10
print(my_list)    # Output: [1, 2, 10, 4, 5]
```

#### List operations:
##### Adding Elements:
- `append()`: Adds a single element to the end of the list.
- `insert()`: Inserts an element at a specific position.
- `extend()`: Adds multiple elements from another list or iterable to the end of the list.
```
my_list.append(6)  # Adds 6 at the end
my_list.insert(2, 7)  # Inserts 7 at index 2
my_list.extend([8, 9])  # Adds 8 and 9 at the end
```
##### Removing elements into list:
- `remove()`: Removes the first occurrence of a value.
- `pop()`: Removes and returns the element at the given index (default is the last element).
- `del statement`: Deletes an element at a specified index.
- `clear()`: Removes all elements from the list.
```
my_list.remove(7)   # Removes the first occurrence of 7
popped_element = my_list.pop(2)  # Removes and returns the element at index 2
my_list.clear()  # Removes all elements
```
##### slice list:
```
newlist = li[2:6] # list containing [2 , 6) elements
newList = li[-4:-1] 
```
##### ==`in`== keyword:
```
li = [3,24345,4,545,34,2,34,2]
if 2 in li:
	print("2 exists in the list")
```
#### Iterating Over Lists:
```
a = ['apple', 'banana', 'cherry']
for item in a:
    print(item)
```
#### Nested Lists and Multidimensional Lists:
```
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Access element at row 2, column 3
print(matrix[1][2])
```

#### Advance syntax:
Creating a List with Repeated Elements:
```
# Create a list [2, 2, 2, 2, 2]
a = [2] * 5

# Create a list [0, 0, 0, 0, 0, 0, 0]
b = [0] * 7

print(a)
print(b)
```





#### List Methods:

|**Method**|**Description**|**Example**|
|---|---|---|
|`append()`|Adds a single element to the end of the list.|`my_list.append(5)` → `[1, 2, 3, 4, 5]`|
|`extend()`|Adds all elements of an iterable (list, tuple, etc.) to the end of the list.|`my_list.extend([6, 7])` → `[1, 2, 3, 4, 5, 6, 7]`|
|`insert()`|Inserts an element at a specified position in the list.|`my_list.insert(2, 10)` → `[1, 2, 10, 3, 4, 5]`|
|`remove()`|Removes the first occurrence of a value in the list.|`my_list.remove(3)` → `[1, 2, 4, 5]`|
|`pop()`|Removes and returns the element at a specified position (default last).|`my_list.pop(1)` → `2` (removes element at index 1)|
|`sort()`|Sorts the elements of the list in ascending order (in-place).|`my_list.sort()` → `[1, 2, 3, 4, 5]`|
|`reverse()`|Reverses the order of elements in the list (in-place).|`my_list.reverse()` → `[5, 4, 3, 2, 1]`|
|`index()`|Returns the index of the first occurrence of a specified value.|`my_list.index(3)` → `2`|
|`count()`|Returns the number of occurrences of a specified value in the list.|`my_list.count(2)` → `1`|
|`clear()`|Removes all elements from the list.|`my_list.clear()` → `[]`|
|`copy()`|Returns a shallow copy of the list.|`new_list = my_list.copy()`|
|`slice()`|Extracts a portion of the list (using slicing syntax).|`my_list[1:4]` → `[2, 3, 4]`|
|`join()`|Joins elements of a list (usually strings) into a single string.|`",".join(["a", "b", "c"])` → `"a,b,c"`|
|`del`|Deletes an element at a specified index or slice.|`del my_list[2]` → `[1, 2, 4, 5]`|
