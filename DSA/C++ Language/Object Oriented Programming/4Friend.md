The `friend` keyword in C++ is used to grant a function or another class **access to the private and protected members** of a class. By default, private and protected members are not accessible outside the class, but with the `friend` keyword, you can allow specific external functions or classes to access these members.
- Friend function is not a member function. ( is not defined inside the class )


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

Example : Create a friend function that compares the area of two rectangles by taking input of rectangle objects.
```
#include <iostream>
using namespace std;
class Rectangle {
private:
    int length, breadth;
public:
    Rectangle(int l, int b) : length(l), breadth(b) {}
    friend bool compareArea(Rectangle& r1, Rectangle& r2);
};

bool compareArea(Rectangle& r1, Rectangle& r2) {
    return r1.breadth * r1.length > r2.breadth * r2.length;
}
int main() {
    Rectangle rect1(30, 20);
    Rectangle rect2(220, 24);
    if (compareArea(rect1, rect2)) {
        cout << "Area of rect1 is greater than rect2" << endl;
    }
    else {
        cout << "Area of rect2 is greater thatn rect1" << endl;
    }
    return 0;
}
```




#### Friend Class
A friend class is a class that has access to the private and protected members of another class.