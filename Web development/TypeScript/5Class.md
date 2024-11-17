#### Definition
- A **class** is a blueprint for creating objects with properties and methods. 
- It is a core feature of object-oriented programming and allows you to define reusable, organized, and strongly typed structures in your code.





#### **Key Components of a Class**

1. **Properties**:
    
    - Variables that belong to the class. They define the state or data the class holds.
2. **Methods**:
    
    - Functions inside the class that define its behavior.
3. **Constructors**:
    
    - A special method used for initializing class properties when an object is created.
4. **Access Modifiers**:
    
    - Control the visibility of properties and methods (`public`, `private`, `protected`).
5. **Type Annotations**:
    
    - TypeScript allows you to specify the types for properties and method parameters.

#### Syntax:
##### 1.  Basic
```
class User{
    username: string;  // properties
    email: string;
    
    constructor(username: string, email: string) {
        this.username = username;
        this.email = email;
    }
    greet() {
        console.log(`Hello ${this.username}`);
    }
}
```
##### 2. Efficient:
```
class User{
    constructor(public username: string,public  email: string) {
    }
    greet() {
        console.log(`Hello ${this.username}`);
    }
}
```
##### Output:
```
class User {
    constructor(username, email) {
        this.username = username;
        this.email = email;
    }
    greet() {
        console.log(`Hello ${this.username}`);
    }
}
```
#### Example:

##### Ex: 1 : 
Create a class with name and age property. Create an username as an inbuild property of the class. Define a method greet that's greets with the name.

TS code:
```
class Person {
    // Properties
    name: string;
    age: number;
    fullname: string = "";  // defult value with no initialization
    
    // Constructor
    constructor(name: string, age: number) {
      this.name = name;
      this.age = age;
    }
    
    // Method
    greet(): string {
      return `Hello, my name is ${this.name}, and I am                  ${this.age} years old.`;
    }
  }

  // Creating an object
  const person1 = new Person("Alice", 25);
  console.log(person1.greet());
```
JS code: Corresponding JS code. 
```
class Person {
    // Constructor
    constructor(name, age) {
        this.name = name;
        this.age = age;
        fullname = "";
}

    // Method
greet() {
        return `Hello, my name is ${this.name}, and I am                  ${this.age} years old.`;
    }
}

	// Creating an object
const person1 = new Person("Alice", 25);
console.log(person1.greet());
```


##### Read-Only Properties:
```
class Book {
  readonly title: string; // cannot be changed

  constructor(title: string) {
    this.title = title;
  }
}

const myBook = new Book("TypeScript Guide");
// myBook.title = "New Title"; // Error: Cannot assign to 'title' because it is a read-only property

```

##### Static Members:
Static properties or methods belong to the class itself, not an instance. It can be accessed without creating an object of the class.
```
class MathUtils {
  static PI = 3.14;

  static circleArea(radius: number): number {
    return this.PI * radius * radius;
  }
}

// 
console.log(MathUtils.PI); // 3.14  
console.log(MathUtils.circleArea(5)); // 78.5

```

#### Access Modifiers:
- Access modifiers determine how and where the properties or methods of a class can be accessed:
1. **`public`** (default):
    - Accessible everywhere.
2. **`private`**:
    - Accessible only within the class.
3. **`protected`**:
    - Accessible within the class and its subclasses.

##### Private:
```
class Employee {
    public name: string; // Accessible everywhere
    private salary: number; // Accessible only inside this class
    constructor(name: string, salary: number) {
      this.name = name;
      this.salary = salary;
    }

    public showSalary(): string {
      return `My salary is ${this.salary}`;
    }
  }

  const emp = new Employee("Bob", 50000);
  console.log(emp.name); // OK

//   console.log(emp.salary); // Error: Property 'salary' is   private

  console.log(emp.showSalary()); // OK
```
##### Protected:
```
class User{
      constructor(public username: string,public  email: string ,       protected platform = "windows") {
      }
      greet() {
          console.log(`Hello ${this.username}`);
      }
}

class Admin extends User{
    isAdmin = true;
    changePlatform() {
        this.platform = "mac";
    }
}
```


#### Getter and Setter
