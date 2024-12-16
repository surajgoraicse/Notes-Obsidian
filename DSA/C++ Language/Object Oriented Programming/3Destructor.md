Destructor is an instance member function that is invoked automatically whenever an object is going to be destroyed. Meaning, a destructor is the last function that is going to be called before an object is destroyed.
- Destructor has the same name as their class name preceded by a tilde (~) symbol.
- It is not possible to define more than one destructor.
- The destructor is only one way to destroy the object created by the constructor. Hence, destructor cannot be overloaded.
- Destructor neither requires any argument nor returns any value.
- Destructor release memory space occupied by the objects created by the constructor.



#### When is the destructor called?
A destructor function is called automatically when the object goes out of scope or is deleted. Following are the cases where destructor is called:

1. Destructor is called when the function ends.
2. Destructor is called when the program ends.
3. Destructor is called when a block containing local variables ends.
4. Destructor is called when a delete operator is called.


#### How to call destructors explicitly?
**Destructor*** can also be called explicitly for an object. We can call the destructors explicitly using the following statement:
```
object_name.~class_name()
```


#### When do we need to write a user-defined destructor?

- If we do not write our own destructor in class, the compiler creates a default destructor for us. 
- **The default destructor works fine unless we have dynamically allocated memory or pointer in class.** 
- When a class contains a pointer to memory allocated in the class, we should write a destructor to release memory before the class instance is destroyed. This must be done to avoid memory leaks.
