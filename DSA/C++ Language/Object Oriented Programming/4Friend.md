The `friend` keyword in C++ is used to grant a function or another class **access to the private and protected members** of a class. By default, private and protected members are not accessible outside the class, but with the `friend` keyword, you can allow specific external functions or classes to access these members.


#### Uses of the `friend` Keyword
1. Friend functions:
   - Sometimes, a function outside the class needs access to the private or protected data of the class.
   - A friend function can access private and protected members directly.
2. Friend Class:
   - A class can declare another class as its friend, allowing the friend class to access its private or protected members.
3. **Operator Overloading**:
   - Used frequently when overloading operators (e.g., `+`, `<<`, `>>`) to access private members of a class.


#### Friend Functions:
A friend function is not a member of the class, but it has access to the class's private and protected members. It must be explicitly declared as a friend within the class.
##### Syntax:
```
class ClassName {
    friend ReturnType FunctionName(Parameters);
};
```
Example : 
```

```