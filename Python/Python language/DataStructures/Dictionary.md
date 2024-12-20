- Dictionaries are used to store data values in key:value pairs.
- A dictionary is a collection which is ordered, changeable and do not allow duplicates.
- Length of the dictionary can be get using len().

Syntax:
```
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
print(thisdict)
```



#### Operations:
##### Access elements:
###### Accessing single values:
1. using square brackets: dist["name"]
2. using get method : get()
   get() can be used to return fall through in case the key - value does not exists.
```
dist = {
    "name"  : "suraj",
    "age" : 10,
    "age" : 21,
    "email" : "suraj@gamil.com"
}
print(dist["name"])
print(dist.get("name"))

# Safe access using get() 
print(my_dict.get("height", "Not found")) 
# Output: Not found
```

###### Accessing multiple values: values()
1. Accessing all the values: 
```
print(dist.values())
# output: dict_values(['suraj', 21, 'suraj@gamil.com'])
```

###### Access all the keys: keys() 
```
print(dist.keys())
# output : dict_keys(['name', 'age', 'email'])
```

###### Accessing all key-value pairs: items()
```
print(dist.items())

# output: dict_items([('name', 'suraj'), ('age', 21), ('email', 'suraj@gamil.com')])
```

###### Check if the keys exists: `in`
```
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
if "model" in thisdict:  
  print("Yes, 'model' is one of the keys in the thisdict dictionary")
```

#### Change Values:
###### Adding / Updating : 
It will update the value if the key exists otherwise it will create a new key value pair.  
```
dist["key"] = "value"
dist.update({"name" : "suraj gorai"})
```

###### Removing:
1. pop() : Removes the item with the specified key name:
```
dist.pop("name")
```
2. popitem() : It removes the last inserted item.
```
dist.popitem()
```
3. del keyword : The `del` keyword removes the item with the specified key name and it can be also used to delete the entire dictionary.
```
del dist["name"]
```
4. clear() : Empties the dictionary.
```
dist.clear()
```

###### Copying:
newDict = dict : will create a shallow copy 
1. copy() : 
```
newDict = dict.copy()
```
2. dict() constructor:
```
newDict = dict({  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
})
```

#### Iterating:
```
for key in my_dict:
    print(key)  # Keys

for value in my_dict.values():
    print(value)  # Values

for key, value in my_dict.items():
    print(key, value)  # Key-Value pairs

```

##### print keys:
```
for key in my_dict:
    print(key)  # Keys
```
##### print values:
```
for x in thisdict:  
  print(thisdict[x])

for x in thisdict.values():  
  print(x)
```

##### print key values:
```
for key in thisdict:
	print(key , thisdict[key])

for x, y in thisdict.items():  
  print(x, y)
```

#### Nested Dictionary:
##### Example 1 : 
```
myfamily = {  
  "child1" : {  
    "name" : "Emil",  
    "year" : 2004  
  },  
  "child2" : {  
    "name" : "Tobias",  
    "year" : 2007  
  },  
  "child3" : {  
    "name" : "Linus",  
    "year" : 2011  
  }  
}
```
##### Example 2: creating multiple dictionary and then using them to create a single dictionary.
```
child1 = {  
  "name" : "Emil",  
  "year" : 2004  
}  
child2 = {  
  "name" : "Tobias",  
  "year" : 2007  
}  
child3 = {  
  "name" : "Linus",  
  "year" : 2011  
}  
  
myfamily = {  
  "child1" : child1,  
  "child2" : child2,  
  "child3" : child3  
}
```


#### Some popular methods:

|**Method**|**Description**|**Example**|**Output**|
|---|---|---|---|
|`dict.keys()`|Returns a view object containing the dictionary's keys.|`d = {"a": 1, "b": 2}; d.keys()`|`dict_keys(['a', 'b'])`|
|`dict.values()`|Returns a view object containing the dictionary's values.|`d = {"a": 1, "b": 2}; d.values()`|`dict_values([1, 2])`|
|`dict.items()`|Returns a view object containing key-value pairs as tuples.|`d = {"a": 1, "b": 2}; d.items()`|`dict_items([('a', 1), ('b', 2)])`|
|`dict.get(key[, default])`|Returns the value for the specified key if present, else returns `default`.|`d = {"a": 1}; d.get("a", 0)`  <br>`d.get("c", 0)`|`1`  <br>`0`|
|`dict.pop(key[, default])`|Removes the specified key and returns its value, or returns `default` if key is absent.|`d = {"a": 1, "b": 2}; d.pop("a")`|`1` (and `d` becomes `{'b': 2}`)|
|`dict.popitem()`|Removes and returns a random (key, value) pair as a tuple (LIFO in Python 3.7+).|`d = {"a": 1, "b": 2}; d.popitem()`|`('b', 2)` (and `d` becomes `{'a': 1}`)|
|`dict.update([other])`|Updates the dictionary with key-value pairs from `other`.|`d = {"a": 1}; d.update({"b": 2})`|`{'a': 1, 'b': 2}`|
|`dict.clear()`|Removes all items from the dictionary.|`d = {"a": 1, "b": 2}; d.clear()`|`{}`|
|`dict.copy()`|Returns a shallow copy of the dictionary.|`d = {"a": 1}; c = d.copy()`|`{'a': 1}`|
|`dict.setdefault(key[, default])`|Returns the value of `key` if it exists; otherwise sets `key` to `default` and returns it.|`d = {"a": 1}; d.setdefault("b", 2)`|`2` (and `d` becomes `{'a': 1, 'b': 2}`)|
|`dict.fromkeys(iterable[, value])`|Creates a new dictionary with keys from `iterable` and all values set to `value`.|`dict.fromkeys(["a", "b"], 0)`|`{'a': 0, 'b': 0}`|
|`dict.__contains__(key)`|Checks if a key exists in the dictionary (using `in` keyword).|`d = {"a": 1}; "a" in d`|`True`|
