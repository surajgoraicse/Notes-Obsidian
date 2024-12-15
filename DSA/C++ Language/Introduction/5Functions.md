



### Pass by reference:
- When a variable is passed as a reference to a function, the address of the variable is stored in a pointer variable inside the function. 
- Hence, the variable inside the function is an alias for the passed variable. 
- Therefore, any operations performed on the variable inside the function will also be reflected in the calling function.

- There are two ways in which a function can receive references.
	- reference ( & ) 
	- pointers ( * )
	- 
 


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


##### Change value using pointers:
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

