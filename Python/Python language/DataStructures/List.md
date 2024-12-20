- A **list** in Python is a collection of ordered, mutable (changeable), and potentially heterogeneous (containing items of different types) elements.
- They are created using square brackets.
- **Ordered**: The items in a list have a defined order, meaning the order of elements is preserved. The first item in the list will always remain the first item unless explicitly changed.



#### Syntax:
```
my_list = [1, 2, 3, 4, 5]
print(my_list)
```
Accessing elements:
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
- `clear()`: Removes all elements from the list.
```
my_list.remove(7)   # Removes the first occurrence of 7
popped_element = my_list.pop(2)  # Removes and returns the element at index 2
my_list.clear()  # Removes all elements
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

