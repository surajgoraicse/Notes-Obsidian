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
**string* ptr = &food;**    // A pointer variable, with the name ptr, that stores the address of food  
  
// Output the value of food (Pizza)  
cout << food << "\n";  
  
// Output the memory address of food (0x6dfed4)  
cout << &food << "\n";  
  
// Output the memory address of food with the pointer (0x6dfed4)  
cout << ptr << "\n";
```

#### Pointer to Pointer
```
int num = 23;
int* ptr = &num;
int** ptrToPtr = &ptr;
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
```
