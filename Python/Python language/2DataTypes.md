#### Number
There are three numeric types in Python:
- `int`
- `float`
- `complex`

```
x = 1    # int  
y = 2.8  # float  
z = 1j   # complex
```

##### Complex:
Complex numbers are written with a "j" as the imaginary part:
```
x = 3+5j  
y = 5j  
z = -5j
```

#### Strings
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