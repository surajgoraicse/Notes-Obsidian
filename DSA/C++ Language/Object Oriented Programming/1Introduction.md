
#### What is object oriented programming ?
- **Object-Oriented Programming (OOP)** is a programming paradigm (style) that organizes code around **objects** rather than functions ( procedural ). 
- Objects represent real-world entities, combining **data** (attributes) and **behaviors** (methods) into a single unit. 
- OOP is based on four main principles: **encapsulation**, **inheritance**, **polymorphism**, and **abstraction**.


#### What is a class ?
- A class is a user-defined data type, and it works as an object constructor, or a "blueprint" for creating objects.
- Function defined inside class are known as member functions.
- Variable or attributes defined inside the class are known as member attributes.
- Member functions and member attributes are collectively known as class members.
- Class name should be capitalized and class should end with semi-colon. ( ; )

example : 
```
class MyClass{
	public:
		int num;  // attributes
		int name;
		void print(){   // member fuctions
			cout<< "number : " << num<<endl;
			cout<< "name : "<< name<<endl;
		}
};
```

##### Member Function in C++ Classes
- They are the function defined in the class.
- It can be accessed by creating an object of class.

###### There are 2 ways to define a member function
- Inside class definition
- Outside class definition
Inline vs non-inline functions:
Inline : Methods defined inside the class are called inline functions.
**Non-inline** : Methods defined outside the class are called inline functions.
**Non-inline** functions can be converted into inline methods by using inline keyword.
syntax : 
`inline void myFun() {  ... definition   }`
  
Example:
```
// C++ program to demonstrate member function
// definition outside class
#include <bits/stdc++.h>
using namespace std;
class Geeks {
public:
    string geekname;
    int id;

    // printname is not defined inside class definition
    void printname();

    // printid is defined inside class definition
    void printid() { cout << "Geek id is: " << id; }
};

// Definition of printname using scope resolution operator
// ::
void Geeks::printname()
{
    cout << "Geekname is: " << geekname;
}
int main()
{

    Geeks obj1;
    obj1.geekname = "xyz";
    obj1.id = 15;

    // call printname()
    obj1.printname();
    cout << endl;

    // call printid()
    obj1.printid();
    return 0;
}
```

#### What is an object ?
- An **object** is an instance of a **class** with some characteristics and behaviors.
- It also represents a real-world entity or concept.
- When a class is defined, no memory is allocated but when it is instantiated (i.e. an object is created) memory is allocated.

#### Creating an object:
An object is created from a class.
```
Syntax :
ClassName objectName;
ClassName2 objectName(para1 , para2);
```

```
MyClass obj;
obj.name = "bullet classic";
obj.num = 0001;
obj.print();
```


#### Access Specifier
- Access specifiers are used to control the access to the members of the class.
- They determine whether a class member can be accessed from outside the class, within the class, or in derived classes.


##### There are 3 types of access specifiers:
1. **Public:** Members declared as public can be accessed from both inside and outside the class.
2. **Private:** Members declared as private can only be accessed within the class. It is also the default access specifier.
3. **Protected:** Members declared as protected can be accessed within the class and by derived classes.








