
A string is a sequence of characters. Python treats anything inside quotes as a string. This includes letters, numbers, and symbols. Python has no character data type so single character is a string of length 1.

Syntax: Strings can be created using either ****single (‘)**** or ****double (“)**** quotes.
```
s1 = 'GfG'
s2 = "GfG"
```

##### Multi-line strings
If we need a string to span multiple lines then we can use ****triple quotes (”’ or “””)****

```
s = """I am Learning
Python String on GeeksforGeeks"""
print(s)

s = '''I'm a 
Geek'''
print(s)
```

##### Accessing characters:
Strings in Python are sequences of characters, so we can access individual characters using **indexing.** Strings are indexed starting from **0** and **-1** from end. This allows us to retrieve specific characters from the string.
![[strings.jpg]]
```
s = "GeeksforGeeks"

# Accesses first character: 'G'
print(s[0])   

# Accesses 5th character: 's'
print(s[4])

# Accesses last character: 's'
print(s[-1])
```


##### String Slicing
Slicing is a way to extract portion of a string by specifying the **start** and **end** indexes. The syntax for slicing is **string[start:end]**, where **start** starting index and **end** is stopping index (excluded).
```
s = "GeeksforGeeks"

# Retrieves characters from index 1 to 3: 'eek'
print(s[1:4])  

# Retrieves characters from beginning to index 2: 'Gee'
print(s[:3])   

# Retrieves characters from index 3 to the end: 'ksforGeeks'
print(s[3:])   

# Reverse a string
print(s[::-1])
```


##### String Immutability:
**Strings in Python are immutable**. This means that they cannot be changed after they are created. If we need to manipulate strings then we can use methods like **concatenation, slicing,** or *formatting* to create new strings based on the original.

```
s = "geeksforGeeks"

# Trying to change the first character raises an error
# s[0] = 'I'  # Uncommenting this line will cause a TypeError

# Instead, create a new string
s = "G" + s[1:]
print(s)
```



##### ascii and character conversion:
###### Convert from ascii to character: chr(ascii)
```
print(chr(65))   // A
```

###### Convert from character to ascii: ord(character)
```
print(ord('c'))  // 99
```

#### Formatting a String:
String formatting in Python allows you to create strings with dynamic content by embedding variables, expressions, or values in a template string.

1. Using f-strings:
   This is the most modern and recommended way to format strings. You prefix the string with `f` and use curly braces `{}` to embed expressions or variables.

```
name = "suraj"
email = "surajgoraicse@gmail.com"
print(f"Hello my name is {name} and my email is {email}")
```
2. Using str.format()
   This method allows you to insert values into placeholders marked by `{}`.
```
name = "suraj"
email = "surajgoraicse@gmail.com"
print("Hello my name is {} and my email is {}".format(name,email))
```

#### ==`in`== keyword:
The `in` keyword checks if a particular substring is present in a string or not.
Return type is Boolean. 
```
s = "GeeksforGeeks"
print("Geeks" in s)
print("GfG" in s)
```
#### Why String are immutable ?   ==todo==

#### String Methods:

| **Method**          | **Description**                                                                             | **Example**                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `str.upper()`       | Converts all characters to uppercase.                                                       | `"hello".upper()` → `'HELLO'`                                               |
| `str.lower()`       | Converts all characters to lowercase.                                                       | `"HELLO".lower()` → `'hello'`                                               |
| `str.capitalize()`  | Capitalizes the first character of the string.                                              | `"hello world".capitalize()` → `'Hello world'`                              |
| `str.title()`       | Converts the first character of each word to uppercase.                                     | `"hello world".title()` → `'Hello World'`                                   |
| `str.strip()`       | Removes leading and trailing whitespace (leading = start , trailing = end).                 | `" hello ".strip()` → `'hello'`                                             |
| `str.lstrip()`      | Removes leading whitespace (or specified characters).                                       | `" hello".lstrip()` → `'hello'`                                             |
| `str.rstrip()`      | Removes trailing whitespace (or specified characters).                                      | `"hello ".rstrip()` → `'hello'`                                             |
| `str.split()`       | Splits a string into a list of substrings based on a delimiter (default: whitespace).       | `"a,b,c".split(",")` → `['a', 'b', 'c']`                                    |
| `str.join()`        | Joins a list of strings with a specified delimiter.                                         | `",".join(['a', 'b', 'c'])` → `'a,b,c'`                                     |
| `str.replace()`     | Replaces all occurrences of a substring with another substring.                             | `"hello world".replace("world", "Python")` → `'hello Python'`               |
| `str.find()`        | Returns the lowest index of a substring. Returns `-1` if not found.                         | `"hello world".find("world")` → `6`                                         |
| `str.index()`       | Like `find()`, but raises `ValueError` if the substring is not found.                       | `"hello world".index("world")` → `6`                                        |
| `str.count()`       | Counts occurrences of a substring.                                                          | `"hello hello".count("hello")` → `2`                                        |
| `str.startswith()`  | Returns `True` if the string starts with the specified prefix.                              | `"hello".startswith("he")` → `True`                                         |
| `str.endswith()`    | Returns `True` if the string ends with the specified suffix.                                | `"hello".endswith("lo")` → `True`                                           |
| `str.isdigit()`     | Returns `True` if all characters are digits.                                                | `"123".isdigit()` → `True`, `"123a".isdigit()` → `False`                    |
| `str.isalpha()`     | Returns `True` if all characters are alphabetic.                                            | `"abc".isalpha()` → `True`, `"abc123".isalpha()` → `False`                  |
| `str.isalnum()`     | Returns `True` if all characters are alphanumeric.                                          | `"abc123".isalnum()` → `True`, `"abc!".isalnum()` → `False`                 |
| `str.isspace()`     | Returns `True` if all characters are whitespace.                                            | `" ".isspace()` → `True`, `" a ".isspace()` → `False`                       |
| `str.zfill(width)`  | Pads the string with zeros on the left to make it of the specified width.                   | `"42".zfill(5)` → `'00042'`                                                 |
| `str.center(width)` | Centers the string in a field of the given width, padding with spaces.                      | `"hello".center(10)` → `' hello '`                                          |
| `str.ljust(width)`  | Left-aligns the string in a field of the given width, padding with spaces.                  | `"hello".ljust(10)` → `'hello '`                                            |
| `str.rjust(width)`  | Right-aligns the string in a field of the given width, padding with spaces.                 | `"hello".rjust(10)` → `' hello'`                                            |
| `str.partition()`   | Splits the string into three parts: before, the separator, and after the separator.         | `"hello world".partition(" ")` → `('hello', ' ', 'world')`                  |
| `str.rpartition()`  | Like `partition()`, but splits at the last occurrence of the separator.                     | `"hello world example".rpartition(" ")` → `('hello world', ' ', 'example')` |
| `str.splitlines()`  | Splits the string at line breaks into a list.                                               | `"hello\nworld".splitlines()` → `['hello', 'world']`                        |
| `str.swapcase()`    | Swaps the case of all characters.                                                           | `"Hello".swapcase()` → `'hELLO'`                                            |
| `str.casefold()`    | Converts the string to lowercase, more aggressive than `lower()` (useful for case folding). | `"ß".casefold()` → `'ss'`                                                   |
| len(str)            | returns the length of the string                                                            | len("hello") → 5                                                            |
