Pointers and References both are mechanisms used to deal with memory, memory address, and data in a program. Pointers are used to store the memory address of another variable whereas references are used to create an alias for an already existing variable.


#### Reference 
When a variable is declared as a [reference](https://www.geeksforgeeks.org/references-in-cpp/), it becomes an alternative name for an existing variable.

```
int num = 232;
int &anotherNum = num;
```

#### Pointer
A **pointer**, is a variable that **stores the memory address as its value**.
```
string food = "Pizza";  // A food variable of type string  
string* ptr = &food;   // A pointer variable, with the name ptr, that stores the address of food  
  
// Output the value of food (Pizza)  
cout << food << "\n";  
  
// Output the memory address of food (0x6dfed4)  
cout << &food << "\n";  
  
// Output the memory address of food with the pointer (0x6dfed4)  
cout << ptr << "\n";

// Output the value stored by the pointer (0x6dfed4)  
cout << *ptr << "\n";
```

#### Pointer to Pointer
```
int num = 23;
int* ptr = &num;
int** ptrToPtr = &ptr;
```

#### Address of Operator ( & )
- It is use of get the memory address of a variable.
- It is the location where the variable is stored on the computer.
```
int val = 23;
cout<< &val;  // prints the memory address of val
```


#### Dereference Operator ( * )
Dereference operator is used to get the value of the variable using pointer variable.
```
int num = 34;
int* ptr = &num;   // declaring pointer
cout<<ptr;         // prints memory address of num
cout<< *ptr;       // prints the value at address ptr.
```


#### Null Pointer
```
int* ptr1;  // holds some garbage memory address
int* ptr2 = NULL; // empty (holds no memory address)
int* ptr3 = 0; // same as above
```


#### Pointer arithmetic 
```
int num = 23;
int* ptr = &num;

*ptr = *ptr + 1;  // value at address ptr = value at address ptr + 1
cout<< *ptr <<endl;  // output : 24

```


#### Void pointer:
syntax: `void *ptr;`

**Note:**
1. void pointers **cannot be dereferenced**. It can, however, be done using typecasting the void pointer.
2. Pointer arithmetic is not possible on pointers of void due to lack of concrete value and size.
```
    void* ptr;   // declaring a void pointer
    string str = "hello world";
    ptr = &str;
    cout << ptr;
	cout<< *ptr;  // error : cannot be dereferenced
```


#### Dangling Pointers
- A dangling pointer is a pointers that holds a memory address of a variable that no more exists.
- This typically happens when the memory that the pointer references has been deallocated or gone out of scope, but the pointer itself still holds the old address.


##### Types of dangling pointers

###### Returning Pointers to Local Variables:
A pointer to a local variable inside a function becomes dangling as soon as the function exits because the variable goes out of scope.
```
#include<iostream> 
using namespace std; 
int * fun() {   
	int x = 10;   
	return &x; 
} 
int main() {    
	int * p = fun();    
	// p points to something which is not    
	// valid anymore    
	cout << * p;    
	return 0; 
}
```

###### Deallocation of Memory (use after free):
If you deallocate memory pointed to by a pointer using `delete` or `free`, but still try to access the pointer, it becomes dangling.
```
int* ptr = new int(5);
delete ptr;  // Memory is deallocated
*ptr = 10;   // Dangling pointer usage (undefined behavior)
```


#### Array

- The name of the array represent the memory address of the first element of the array. It is like a pointer. eg. if arr is an array then arr , arr + 1 , arr + i etc are pointers.
- Dereferencing a array pointer using dereference operator ( * ).  : *arr , *(arr + 1 )        *(arr + i) etc.


```
int arr[] = {324,4,5,45,4,5234,32,4};

cout<< arr <<endl;  // prints : memory address of first element of array
cout<< arr + 1 <<endl; // prints memory address of second element

cout<< *arr << endl; // dereferece or prints first element 
cout<< *(arr + 1) << endl; // prints second element

cout<< *arr + 1 << endl; // prints first element + 1
cout<< *(arr + 1) + 1 <<endl; // prints second element + 1


```