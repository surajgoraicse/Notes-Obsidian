
#### Default Parameter:
A parameter with a default value, is often known as an "**optional parameter**".
```
#include<iostream>
using namespace std;
void print(string country = "India"); // default parameter
int main() {
    print("");
    return 0;
}

void print(string country ) {
    cout << country << endl;
}
```

```
#include<iostream>
using namespace std;
void print(string country = "India" ) {
    cout << country << endl;
}
int main() {
    print();
    return 0;
}
```


### Pass by reference:
- When a variable is passed as a reference to a function, the address of the variable is stored in a pointer variable inside the function. 
- Hence, the variable inside the function is an alias for the passed variable. 
- Therefore, any operations performed on the variable inside the function will also be reflected in the calling function.
- Generally they don't have a return type.

- There are two ways in which a function can receive references.
	- reference ( & ) 
	- pointers ( * )

 


#### Manipulation using reference: 
##### Change value using pass by reference:
```
#include<iostream>
using namespace std;
void changeValue(int&);
int main() {
    int a = 10;
    cout << "value of a :" << a << endl;
    changeValue(a);
    cout << "value of a :" << a << endl;
    return 0;
}
void changeValue(int& val) {
    val = val * 10;  
}
```

##### Swap value using reference
```
#include<iostream>
using namespace std;
void swap(string&, string&);
int main() {
    string firstName = "suraj"; // define variables
    string secondName = "gorai";
    
    cout << "firstName = " << firstName << "& secondName " << secondName << endl;
    swap(firstName, secondName);
    cout << "firstName = " << firstName << "& secondName " << secondName << endl;
    return 0;
}

void swap(string& first , string& second) {
    string temp;
    temp = first;
    first = second;
    second = temp;
}
```





#### Manipulation using Pointers:
- Here the function parameter will be a pointer and argument will be a reference or memory address.


##### using pointers:
```
#include<iostream>
using namespace std;
void changeVal(int*);
int main() {
    int val = 10;
    changeVal(&val);
    cout << val << endl;
    return 0;
}
void changeVal(int* ptr) {
    *ptr = *ptr * 10;
}
```
##### swap values using pointer:
```
#include<iostream>
using namespace std;
void swap(string* first, string* second);
int main() {
    string fname = "suraj";
    string lname = "gorai";
    cout << "first name = " << fname << "  last name = " << lname << endl;
    swap(&fname, &lname);
    cout << "first name = " << fname << "  last name = " << lname << endl;
    return 0;
}

void swap(string* first , string* second) {
    string temp = *first;
    *first = *second;
    *second = temp;
}
```


#### When to use Pass by reference or pointer:

1. Avoiding Copy of Large Data : 
   Imagine a function that has to receive a large-sized object, if we pass it without reference, a new copy of it is created which causes a waste of CPU time and memory. We can use references or pointers to avoid this.
2. To Achieve Run Time Polymorphism in a Function:
   We can make a function polymorphic by passing objects as references (or pointers) to it instead of the actual objects. It allows us to achieve runtime polymorphism in our program.

```
#include <iostream>
using namespace std;

// Define the base class structure
struct Base {
    virtual void show() { cout << "In base\n"; }
};

// Define the derived class structure
struct Derived : public Base {
    // Override for Derived behavior
    void show() override { cout << "In derived\n"; }
};

// Function to print using polymorphism
void print(Base* base) { base->show(); }

// driver code
int main(void)
{
    Base b;
    Derived d;

    print(&b);

    print(&d);

    return 0;
}
```
3. ==`To Return Multiple Values:`==
   When we want to return multiple values from a function, passing pointers as function parameters allows us to modify the values of variables passed to the function.
	

#### Return an array from a function:
##### Return a pointer:
- You can return a pointer to the first element of the array. 
- However, ensure the array's lifetime outlives the function call.
- and also the length of the array.
```
#include <iostream>
using namespace std;

int* createArray() {
    static int arr[5] = {1, 2, 3, 4, 5}; 
    // Static to ensure it persists after the function ends
    return arr;
}

int main() {
    int* arr = createArray();
    for (int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
```

##### Pass an Array as a Function Parameter:
- You can pass an array to a function and modify it directly, avoiding the need to "return" the array.
```
#include <iostream>
using namespace std;

void fillArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        arr[i] = i + 1;
    }
}

int main() {
    int arr[5];
    fillArray(arr, 5);
    for (int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

```

##### Using dynamic memory allocation:
You can allocate an array dynamically using `new` and return a pointer. Be cautious about memory leaks and proper deallocation.
```
#include <iostream>
using namespace std;

int* createArray(int size) {
    int* arr = new int[size];
    for (int i = 0; i < size; i++) {
        arr[i] = i + 1;
    }
    return arr;
}

int main() {
    int size = 5;
    int* arr = createArray(size);
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    delete[] arr; // Free allocated memory
    return 0;
}

```






#### Function Overloading
With **function overloading**, multiple functions can have the same name with different parameters:

```
int myFunction(int x)  
float myFunction(float x)  
double myFunction(double x, double y)
```