
#### syntax:
A function is defined using the def keyword:
```
def my_function():  
  print("Hello from a function")

my_function()  # calling a function
```

##### Arguments and parameters:
```
def my_function(fname):  
  print(fname + " Refsnes")  
  
my_function("Emil")  
my_function("Tobias")  
my_function("Linus")
```

#### Variable number of arguments:
If we do not know how many arguments that will be passed into your function, add a `*` before the parameter name in the function definition.

```
def fn(*val):
    print(val)
    print(val[len(val) - 1])

fn("suraj" , "akash" , "suravi" , "sukumar")
```

#### Keyword Arguments
Sending arguments with the _key_ = _value_ syntax.
```
def my_function(child3, child2, child1):  
  print("The youngest child is " + child3)  
  
my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```
