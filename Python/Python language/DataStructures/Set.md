- Sets are unordered collection of data items. 
- They store multiple items in a single variable. 
- Sets items are separated by commas and enclosed within curly brackets {}. 
- Sets are unchangeable, meaning you cannot change items of the set once created. Sets do not contain duplicate items.
- the items of set occur in random order and hence they cannot be accessed using index numbers. 


#### Syntax:
```
my_set = {1, 2, 3}
my_set = set([1, 2, 3, 3]) # Removes duplicates
```

#### Operations:
1. The values `True` , `False` and `1` , `0` respectively  are considered the same value in sets, and are treated as duplicates:
```
s = {1 , True , 0 , False}
print(s)
# output {0, 1}
```

##### Access elements:
We cannot access items in a set by referring to an index or a key.
But we can iterate through the set using for loop:
```
thisset = {"apple", "banana", "cherry"}  
  
for x in thisset:  
  print(x)
```

##### Adding items: 
1. add()
```
s = {"one" , "two" , "three"}
s.add("four")
```
2. update()
   It can be used to add elements from another set:
```
thisset = {"apple", "banana", "cherry"}  
tropical = {"pineapple", "mango", "papaya"}  
  
thisset.update(tropical)  
  
print(thisset)
```
3. Add elements from any iterable.
   The object in the update() method does not have to be a set, it can be any iterable object like tuples, dictionary or list.
```
thisset = {"apple", "banana", "cherry"}  
mylist = ["kiwi", "orange"]  
  
thisset.update(mylist)  
  
print(thisset)
```

##### Remove Elements:
To remove an item in a set, use the `remove()`, or the `discard()` method.
1. remove() : 
   If the item to remove does not exist, `remove()` will raise an error.
```
thisset = {"apple", "banana", "cherry"}  
  
thisset.remove("banana")  
  
print(thisset)
```
2. discard():
   If the item to remove does not exist, `discard()` will **NOT** raise an error.
```
thisset = {"apple", "banana", "cherry"}  
  
thisset.discard("banana")  
  
print(thisset)
```
3. clear() : 
   empties the entire set
```
thisset = {"apple", "banana", "cherry"}  
  
thisset.clear()  
  
print(thisset)
```
4. del keyword:
   del keyword will delete the set completely
```
thisset = {"apple", "banana", "cherry"}  
  
del thisset  
  
print(thisset)
```


#### Set special methods:
There are several ways to join two or more sets in Python.
- The `union()` and `update()` methods joins all items from both sets.
- The `intersection()` method keeps ONLY the duplicates.
- The `difference()` method keeps the items from the first set that are not in the other set(s).
- The `symmetric_difference()` method keeps all items EXCEPT the duplicates.

|**Method**|**Description**|**Example**|**Output**|
|---|---|---|---|
|`union()`|Combines all unique items from both sets.|`{1, 2}.union({2, 3})`|`{1, 2, 3}`|
|`update()`|Adds all unique items from another set to the original set.|`s1 = {1, 2}; s1.update({2, 3})`|`s1 = {1, 2, 3}`|
|`intersection()`|Keeps only items common to both sets.|`{1, 2, 3}.intersection({2, 3, 4})`|`{2, 3}`|
|`difference()`|Keeps items in the first set that are not in others.|`{1, 2, 3}.difference({2, 3, 4})`|`{1}`|
|`symmetric_difference()`|Keeps all items except those present in both sets.|`{1, 2, 3}.symmetric_difference({2, 3, 4})`|`{1, 4}`|
##### union:
- The `union()` method returns a new set with all items from both sets.
- We can also use the `|` operator instead of the `union()` method, and you will get the same result.
- It can also be used to join different iterable data types like tuples or list.
```
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
  
set3 = set1.union(set2)  
set4 = set1 | set2
print(set3) 
print(set4)
# output {1, 2, 3, 'a', 'c', 'b'}
```
- Join multiple set:
```
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
set3 = {"John", "Elena"}  
set4 = {"apple", "bananas", "cherry"}  
  
myset = set1.union(set2, set3, set4)  
myset = set1 | set2 | set3 |set4
print(myset)
```

##### Intersection:
- The `intersection()` method will return a new set, that only contains the items that are present in both sets (duplicates).
- We can use the `&` operator instead of the `intersection()` method, and you will get the same result.
- The `&` operator only allows you to join sets with sets, and not with other data types like you can with the `intersection()` method.
- The `intersection_update()` method will also keep ONLY the duplicates, but it will change the original set instead of returning a new set.
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set3 = set1.intersection(set2)  
set3 = set1 & set2
print(set3)
# ouput : apple
```
intersection_update():
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.intersection_update(set2)  
  
print(set1)
```

##### Difference:
- The `difference()` method will return a new set that will contain only the items from the first set that are not present in the other set.
- We can use the `-` operator instead of the `difference()` method, and you will get the same result.
- The `-` operator only allows you to join sets with sets, and not with other data types like you can with the `difference()` method.
- The `difference_update()` method will also keep the items from the first set that are not in the other set, but it will change the original set instead of returning a new set.


Keep all items from set1 that are not in set2:
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set3 = set1.difference(set2) 
# set3 = set1 - set2  
  
print(set3)
```

difference_upadte():
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.difference_update(set2)  
  
print(set1)
```

##### Symmetric Difference:
- The `symmetric_difference()` method will keep only the elements that are NOT present in both sets.
- We can use the `^` operator instead of the `symmetric_difference()` method, and you will get the same result.
- The `^` operator only allows you to join sets with sets, and not with other data types like you can with the `symmetric_difference()` method.
- The `symmetric_difference_update()` method will also keep all but the duplicates, but it will change the original set instead of returning a new set.
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set3 = set1.symmetric_difference(set2)  
set3 = set1 ^ set2

print(set3)
```
`symmetric_difference_update()`
```
set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.symmetric_difference_update(set2)  
  
print(set1)
```


#### Methods:

|**Method**|**Description**|**Example**|**Output**|
|---|---|---|---|
|`add(x)`|Adds an element `x` to the set.|`s = {1, 2}; s.add(3)`|`{1, 2, 3}`|
|`remove(x)`|Removes an element `x` from the set. Raises `KeyError` if `x` is not found.|`s = {1, 2, 3}; s.remove(2)`|`{1, 3}`|
|`discard(x)`|Removes an element `x` if it exists. Does nothing if `x` is not found.|`s = {1, 2, 3}; s.discard(4)`|`{1, 2, 3}`|
|`pop()`|Removes and returns an arbitrary element from the set.|`s = {1, 2, 3}; s.pop()`|`1` (or another value)|
|`clear()`|Removes all elements from the set.|`s = {1, 2, 3}; s.clear()`|`set()`|
|`union(*others)`|Returns a new set containing all unique elements from the set and the specified sets.|`{1, 2}.union({2, 3})`|`{1, 2, 3}`|
|`update(*others)`|Adds all elements from the specified sets to the current set.|`s = {1, 2}; s.update({2, 3})`|`{1, 2, 3}`|
|`intersection(*others)`|Returns a new set containing elements common to the set and the specified sets.|`{1, 2, 3}.intersection({2, 3, 4})`|`{2, 3}`|
|`intersection_update(*others)`|Keeps only the common elements between the set and the specified sets.|`s = {1, 2, 3}; s.intersection_update({2, 3, 4})`|`{2, 3}`|
|`difference(*others)`|Returns a new set containing elements in the set but not in the specified sets.|`{1, 2, 3}.difference({2, 3, 4})`|`{1}`|
|`difference_update(*others)`|Removes elements found in the specified sets from the set.|`s = {1, 2, 3}; s.difference_update({2, 3, 4})`|`{1}`|
|`symmetric_difference(other)`|Returns a new set containing elements in either set but not in both.|`{1, 2, 3}.symmetric_difference({2, 3, 4})`|`{1, 4}`|
|`symmetric_difference_update(other)`|Updates the set with elements in either set but not in both.|`s = {1, 2, 3}; s.symmetric_difference_update({2, 3, 4})`|`{1, 4}`|
|`issubset(other)`|Checks if the set is a subset of `other`.|`{1, 2}.issubset({1, 2, 3})`|`True`|
|`issuperset(other)`|Checks if the set is a superset of `other`.|`{1, 2, 3}.issuperset({1, 2})`|`True`|
|`isdisjoint(other)`|Checks if the set has no elements in common with `other`.|`{1, 2}.isdisjoint({3, 4})`|`True`|
|`copy()`|Returns a shallow copy of the set.|`s = {1, 2, 3}; c = s.copy()`|`{1, 2, 3}`|