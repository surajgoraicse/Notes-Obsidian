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

#### Example:

##### Ex: 1 

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
JS code:
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

##### Ex 2:

