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
#### Implements in Class using Interface
- The `implements` keyword is used to enforce that a class follow strictly to the structure of an interface. 
- It ensures that the class implements all the properties and methods defined in the interface. 
- It helps in creating a strongly-typed, reusable code.
##### Steps to use:
1. Define interface:
	- An interface is a contract that specifies the structure (properties and methods) that a class must implement.
2. Use implements in the class:
	- A class uses the `implements` keyword to declare that it will follow the interface's structure.
	- A class can implement multiple interfaces by separating them with commas.
##### Syntax:
```
interface Person {
  name: string;
  greet(): string;
}

interface Employee {
  employeeId: number;
  work(): string;
}

class Manager implements Person, Employee {
  name: string;
  employeeId: number;

  constructor(name: string, employeeId: number) {
    this.name = name;
    this.employeeId = employeeId;
  }

  greet(): string {
    return `Hi, I'm ${this.name}.`;
  }

  work(): string {
    return `Managing employees with ID: ${this.employeeId}`;
  }
}

const manager = new Manager("Bob", 101);
console.log(manager.greet()); // Hi, I'm Bob.
console.log(manager.work());  // Managing employees with ID: 101
```

#### Abstract Classes
- An **abstract class** in TypeScript is a class that cannot be instantiated directly. 
- It serves as a blueprint for other classes and often contains common properties or methods shared by its subclasses. 
- Abstract classes are part of object-oriented programming (OOP) and are used to enforce structure while allowing subclasses to implement specific behavior.


##### **Key Features of Abstract Classes**

1. **Cannot Be Instantiated**:
    - You cannot create an object of an abstract class.
2. **Abstract Methods**:
    - Defined in the abstract class but do not have an implementation. Subclasses must provide the implementation.
    - Declared using the `abstract` keyword.
3. **Can Have Concrete Methods**:
    - An abstract class can also have methods with implementation that can be inherited by subclasses.
4. **Can Include Properties**:
    - Abstract classes can have properties with or without default values.

##### Syntax:
```
abstract class Animal {
  abstract makeSound(): void; // Abstract method

  move(): void {
    console.log("Moving..."); // method
  }
}

class Dog extends Animal {  // sub-class
  makeSound(): void {
    console.log("Woof! Woof!");
  }
}

const dog = new Dog();   // instance of the class
dog.move(); // Output: Moving...
dog.makeSound(); // Output: Woof! Woof!

// const animal = new Animal(); // Error: Cannot create an instance of an abstract class.

```



##### Use Cases for Abstract Classes

- **Common Behavior**:
    - When multiple subclasses share some common functionality, abstract classes can provide a base implementation.
- **Enforcing Structure**:
    - Abstract methods enforce that subclasses must implement certain methods, ensuring consistency.
- **Polymorphism**:
    - Abstract classes enable polymorphism, allowing you to treat subclasses as their abstract superclass.

