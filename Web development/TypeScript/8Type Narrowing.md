
#### What is Type Narrowing in TypeScript?
- **Type narrowing** is a process in TypeScript where the type of a variable is refined or restricted to a more specific type based on runtime checks. 
- This allows TypeScript to provide better type safety and enable more accurate autocomplete suggestions during development.

#### Why is Type Narrowing Useful?
- **Improved Type Safety**:
    - Ensures operations are performed only on compatible types.
- **Enhanced Developer Experience**:
    - Provides better IntelliSense and eliminates unnecessary type casting.
- **Reduces Runtime Errors**:
    - Errors are caught at compile time instead of runtime.

#### **Techniques for Type Narrowing**

1. **`typeof` Check**
2. **`instanceof` Check**
3. **Equality (`===` or `!==`)**
4. **`in` Operator**
5. **Custom Type Guards**
6. **Control Flow Analysis**
7. **Discriminated Unions**

#### Syntax:
###### `typeof` Check : 
The `typeof` operator is used to narrow types for primitive values.
```
function processValue(value: string | number) {
  if (typeof value === "string") {
    console.log(value.toUpperCase()); // Narrowed to string
    return;
  } else {
    console.log(value.toFixed(2)); // Narrowed to number
  }
}

// Example 2:
function fn1(val: string | null): void{

    if (!val) {

        console.log("please provide a value");

    }

    val?.toUpperCase();

}
```
###### `instanceof` Check : 
The `instanceof` operator is used to narrow types for objects based on their constructor.
```
class Dog {
  bark() {
    console.log("Woof!");
  }
}

class Cat {
  meow() {
    console.log("Meow!");
  }
}

function makeSound(animal: Dog | Cat) {
  if (animal instanceof Dog) {
    animal.bark(); // Narrowed to Dog
  } else {
    animal.meow(); // Narrowed to Cat
  }
}

```

###### Equality (`===` or `!==`) :
```
function checkValue(value: string | null) {
  if (value === null) {
    console.log("Value is null"); // Narrowed to null
  } else {
    console.log(value.toLowerCase()); // Narrowed to string
  }
}

```

###### `in` Operator: 
The `in` operator checks for the presence of a property, narrowing the type to objects that have that property.
```
type Fish = { swim: () => void };
type Bird = { fly: () => void };

function move(animal: Fish | Bird) {
  if ("swim" in animal) {
    animal.swim(); // Narrowed to Fish
  } else {
    animal.fly(); // Narrowed to Bird
  }
}

```

 ###### Custom Type Guards: `is` operator
Custom type guards are functions that explicitly check and narrow types.

```
type Fish = {
    swim():void
}

type Bird = {
    fly():void
}

// this will not work
// function isFish(animal: Fish | Bird){
//  return (animal as Fish).swim !== undefined;
// }

function isFish(animal: Fish | Bird): animal is Fish {
  return (animal as Fish).swim !== undefined;
}

function move(animal: Fish | Bird) {
  if (isFish(animal)) {
    animal.swim(); // Narrowed to Fish
  } else {
    animal.fly(); // Narrowed to Bird
  }
}

```

###### Control Flow Analysis: 
TypeScript tracks the flow of your code to narrow types automatically.
```
function printId(id: string | number | undefined) {
  if (id === undefined) {
    console.log("No ID provided"); // Narrowed to undefined
  } else if (typeof id === "string") {
    console.log(id.toUpperCase()); // Narrowed to string
  } else {
    console.log(id.toFixed(2)); // Narrowed to number
  }
}
```
###### Discriminated Unions: 
Discriminated unions are a pattern that uses a common property (discriminator) to distinguish between different types.
```
type Circle = { kind: "circle"; radius: number };
type Square = { kind: "square"; side: number };

type Shape = Circle | Square;

function getArea(shape: Shape) {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2; // Narrowed to Circle
    case "square":
      return shape.side ** 2; // Narrowed to Square
  }
}

```

#### `in` operator:
- The **`in`** operator in TypeScript is used to check if a **property** exists on an object. 
- It works for both object literals and class instances. 
- This operator is often used in **type narrowing** to distinguish between different object types in a union.

##### Syntax:
```
// propertyName in object

const obj = { name: "Alice", age: 25 }; 
console.log("name" in obj); // true 
console.log("address" in obj); // false
```

###### Using in class:
```
interface User{
    name: string,
    email: string
}
interface Admin{
    name: string,
    email: string,
    isAdmin: boolean
}
// function to check whether object is admin or not

function isAdminAccount(account: User | Admin) {
    // account.isAdmin (not a valid statement as isAdmin is only         in Admin)
    // type narrowing

    if ("isAdmin" in account) {
        return account.isAdmin
    }
}
```


#### Exhaustiveness Checking:

```
interface Square {
    type: "square";
    side: number;
}
interface Rectangle {
    type: "rectangle";
    length: number;
    bredth: number;
}
interface Circle {
    type: "circle";
    radius: number;
}

type Shape = Square | Rectangle | Circle;  //define a type

// one way of implementation
function getShapeArea(shape: Shape) {
    if (shape.type === "square") {
        return shape.side * shape.side;
    } else if (shape.type === "rectangle") {
        return shape.length * shape.bredth;
    } else {
        return shape.radius * shape.radius * Math.PI;
    }
}

// another way
function getArea(shape: Shape) {
    switch (shape.type) {
        case "circle": {
            return shape.radius * shape.radius * Math.PI;
            break;
        }
        case "rectangle": {
            return shape.length * shape.bredth;
            break;
        }
        case "square": {
            return shape.side * shape.side;
            break;
        }
        default:

      const _exhaustiveCheck: never = shape;   
      // should have a default case
    }
}
```