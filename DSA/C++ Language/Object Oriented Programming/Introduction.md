
#### What is object oriented programming ?
- **Object-Oriented Programming (OOP)** is a programming paradigm (style) that organizes code around **objects** rather than functions ( procedural ). 
- Objects represent real-world entities, combining **data** (attributes) and **behaviors** (methods) into a single unit. 
- OOP is based on four main principles: **encapsulation**, **inheritance**, **polymorphism**, and **abstraction**.


#### What is a class ?
- A class is a user-defined data type, and it works as an object constructor, or a "blueprint" for creating objects.
- Function defined inside class are known as member functions.
- Variable or attributes defined inside the class are known as member attributes.
- Member functions and member attributes are collectively known as class members.

example : 
```
class MyClass{
	public:
		int num;  // attributes
		int name;
		void print(){   // fuctions
			cout<< "number : " << num<<endl;
			cout<< "name : "<< name<<endl;
		}
};
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


There are 3 types of access specifiers:

1. **Public:** Members declared as public can be accessed from both inside and outside the class.
2. **Private:** Members declared as private can only be accessed within the class.
3. **Protected:** Members declared as protected can be accessed within the class and by derived classes.








