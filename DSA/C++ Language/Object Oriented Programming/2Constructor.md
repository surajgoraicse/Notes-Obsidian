- ***Constructor in C++***  is a special method that is invoked automatically at the time an object of a class is created. 
- It is used to initialize the data members of new objects generally. 
- The constructor in C++ has the same name as the class or structure. 
- It constructs the values i.e. provides data for the object which is why it is known as a constructor.
- Constructors are mostly declared in the public section of the class though they can be declared in the private section of the class.
- Constructors do not return values; hence they do not have a return type.
- we can have more than one constructor in a class. It is called Constructor Overloading.



#### Constructor Parameters
- Constructors can also take parameters (just like regular functions), which can be useful for setting initial values for attributes.

```
#include<iostream>
using namespace std;
class Car {
public:
    string brand;
    string model;
    int manufacturingYear;
    Car(string b, string m , int yr) {
        brand = b;
        model = m;
        manufacturingYear = yr;
    }
    void printDetails() {
        cout << "Brand : " << brand << endl;
        cout << "Model : " << model << endl;
        cout << "manufacturing year : " << manufacturingYear << endl;
    }
};

int main() {
    Car myCar("Toyota" , "Fortuner" , 2025);
    myCar.printDetails();
    return 0;
}
```

##### Defining constructor function outside the class:
Just like functions, constructors can also be defined outside the class. First, declare the constructor inside the class, and then define it outside of the class by specifying the name of the class, followed by the scope resolution `::` operator, followed by the name of the constructor (which is the same as the class):
```
class Car {        // The class  
  public:          // Access specifier  
    string brand;  // Attribute  
    string model;  // Attribute  
    int year;      // Attribute  
    Car(string x, string y, int z); // Constructor declaration  
};  
  
// Constructor definition outside the class  
Car::Car(string x, string y, int z) {  
  brand = x;  
  model = y;  
  year = z;  
}  
  
int main() {  
  // Create Car objects and call the constructor with different values  
  Car carObj1("BMW", "X5", 1999);  
  Car carObj2("Ford", "Mustang", 1969);  
  
  // Print values  
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";  
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";  
  return 0;  
}
```


#### Types of constructor:
Constructors can be classified based on in which situations they are being used. There are 4 types of constructors in C++:

1. ***Default Constructor**: No parameters. They are used to create an object with default values.
2. **Parameterized Constructor**: Takes parameters. Used to create an object with specific initial values.
3. **Copy Constructor**: Takes a reference to another object of the same class. Used to create a copy of an object.
4. **Move Constructor**: The move constructor creates the object from an already existing object but by moving it.

##### Default Constructor : 
A **default constructor*** is a constructor that either takes no arguments or has default values for all its parameters. They are used to create an object with default values.
```
#include<iostream>
using namespace std;
class Car {
public:
    string brand;
    string model;
    string year;
    Car() {
        brand = "Toyota";
        model = "Fortuner";
        year = "2025";
    }
    void printDetails() {
        cout << "Brand : " << brand << endl;
        cout << "model : " << model << endl;
        cout << "Year : " << year << endl;
    }
};
int main() {
    Car myCar;
    myCar.printDetails();
}
```

##### Parameterized Constructor 
Parameterized constructor is a type of constructor that can accept arguments. Parameterized Constructors make it possible to pass arguments to initialize an object when it is created.
```
#include<iostream>
using namespace std;
class Car {
public:
    string brand;
    string model;
    string year;
    Car() {
        brand = "Toyota";
        model = "Fortuner";
        year = "2025";
    }
    void printDetails() {
        cout << "Brand : " << brand << endl;
        cout << "model : " << model << endl;
        cout << "Year : " << year << endl;
    }
};
int main() {
    Car myCar;
    myCar.printDetails();
}
```

##### Copy Constructor:
A ***copy constructor** is a type of constructor that initializes an object using another object of the same class. In simple terms, a constructor which creates an object by initializing it with an object of the same class, which has been created previously is known as a **copy constructor***.

```
#include<iostream>
using namespace std;
class Student {
    int rno;
    string name;
    double fees;
public:
    // parameterised constructor
    Student(int r, string na, double fe) {
        cout << "Parameterized constructor executed" << endl;
        rno = r;
        name = na;
        fees = fe;
    }

    // copy constructor
    Student(Student& st) {
        cout << "Copy constructor executed" << endl;
        rno = st.rno;
        name = st.name;
        fees = st.fees;
    }

    void printDetails() {
        cout << "Name : " << name << endl;
        cout << "Roll number : " << rno << endl;
        cout << "Fees : " << fees << endl;
        cout << endl;
    } 
};

int main() {
    // creating object
    Student st1(7, "Suraj", 40000.0);
    Student st2(st1);
    st1.printDetails();
    st2.printDetails();
    return 0;
}
```






#### Constructor Overloading
We can have more than one constructor in a class with same name, as long as each has a different list of arguments. This concept is known as Constructor Overloading.

```
// C++ program to illustrate 
// Constructor overloading 
#include <iostream> 
using namespace std; 

class construct 
{ 
public: 
	float area; 

	// Constructor with no parameters 
	construct() 
	{ 
		area = 0; 
	} 
	
	// Constructor with two parameters 
	construct(int a, int b) 
	{ 
		area = a * b; 
	} 
	
	void disp() 
	{ 
		cout<< area<< endl; 
	} 
}; 

int main() 
{ 
	// Constructor Overloading 
	// with two different constructors 
	// of class name 
	construct o; 
	construct o2( 10, 20); 
	
	o.disp(); 
	o2.disp(); 
	return 1; 
} 

```