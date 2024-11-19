#### Definitions
TypeScript is a development tool which helps to write better javascript code.


#### Types in TS:
1. Primitives : string , number, boolean, bigint and symbol.
2. Special Types : any, unknown, void, null, undefined, never.
3. Object Types : Arrays, Tuples, object, Record and Map/Set.
4. User defined types : Interface,  Type Aliases, Enums, Union types, and Intersection types.
#### Syntax:

Primitive Types:
let variableName : type = value;
`let greeting: string = "Hello Suraj";`
```
let age: number = 25;
let name: string = "Alice";
let isStudent: boolean = true;
```


#### When types are not recommended ?
When values are assigned immediately then types are generally not recommended.
```
const name = "Suraj";
console.log(name);
```

#### any 
Allows any type, disabling type checking.
```
let value: any;
function getValue() {
    return "hello";
}
value = getValue();
console.log(value);
value = 3434;
console.log(value);
```

#### void and never

```
function consoleError(error : string):void{
console.log(error)
}
```

The `never` type represents values which are _never_ observed. In a return type, this means that the function ==`throws an exception or terminates`== execution of the program.

```
function fail(msg: string): never {
throw new Error(msg);
}
```

#### Type Aliases 
Creating a custom data type:
```
type User = {
	name : string;
	email: string;
	isActive: boolean;
}
type customData = string | number;

function createUser(user : User):void{
}
```

```
type StringOrNumber = string | number;
let value: StringOrNumber; 
value = "Hello"; // valid 
value = 42; // also valid
```

##### Combining types: 
`type newType = type1 & type2;`

```
type cardDate = {
    cardDate: String
}
type cardDetails = {
    cvv: number;
    cardNumber: number;
}
type creditCard = cardDate & cardDetails & { isActive: true };
```
#### Interface
- An **interface** is a way to define the shape of an object. 
- It is used to specify what properties and methods an object should have and their types, without providing any implementation.
##### Syntax:
```
interface InterfaceName { 
	propertyName: type; 
	methodName(parameter: type): returnType; 
}
```
##### Example:
```
interface Person { 
	name: string; 
	age: number; 
	greet(): void; 
}

// using the interface
const user: Person = { 
	name: "Alice", 
	age: 25, 
	greet() { 
		console.log("Hello, my name is " + this.name); 
	}, 
}; 
user.greet(); // Output: Hello, my name is Alice
```
##### Key Features of Interfaces:
**Optional Properties**: Use `?` to mark a property as optional.
```
interface Person { 
	name: string; 
	age?: number; // This property is optional 
} 
const user: Person = { name: "Alice" }; // Valid
```
**Readonly Properties**: Use `readonly` to make a property immutable.
```
interface Person {
  readonly id: number;
  name: string;
}

const user: Person = { id: 1, name: "Alice" };
user.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.

```
**Functions in Interfaces**: You can define methods (functions) directly in an interface.
```
interface Calculator {
  add(a: number, b: number): number;
  subtract(a: number, b: number): number;
}

const calculator: Calculator = {
  add: (a, b) => a + b,
  subtract: (a, b) => a - b,
};
```
**Extending Interfaces**: You can create a new interface by extending an existing one.
```
// Syntax : interface Inter1 extends Inter2, Inter3{}

interface Animal {
  name: string;
}

interface Dog extends Animal {
  breed: string;
}

const myDog: Dog = { name: "Buddy", breed: "Golden Retriever" };
```
**Reopening of the interface**
```
interface User{
    fullname: String;
    username: String;
    password: String;
}

interface User{
    isLoggedIn: boolean;
}

const newUser: User = {
    fullname: "suraj gorai",
    username: "surajgoraicse",
    password: "3243dfdf",
    isLoggedIn: false
}
```
#### Difference between Type and Interface:
| **Aspect**                | **Type**                                                                                               | **Interface**                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| **Definition**            | `type` is used to create type aliases for any type, such as primitives, unions, tuples, or objects.    | `interface` is used to define the structure or blueprint of objects, focusing on object shapes and behavior.         |
| **Flexibility**           | Can represent complex types like unions, intersections, primitives, and arrays.                        | Primarily designed to define object structures but can also define callable types or indexable types.                |
| **Use Cases**             | Works well for defining unions, tuples, or aliasing more complex types.                                | Ideal for object-oriented programming, where the focus is on designing the shape and behavior of objects.            |
| **Extension/Inheritance** | Cannot use `extends`, but you can combine types using intersections (`&`). Example: `type A = B & C;`. | Can use the `extends` keyword to inherit properties from other interfaces. Example: `interface A extends B { }`.     |
| **Declaration Merging**   | Does not support merging. If you declare `type A` twice, it results in an error.                       | Supports merging. If you declare `interface A` multiple times, TypeScript will merge their properties automatically. |
| **Reusability**           | Can be reused with intersections for combining types, but lacks inheritance support.                   | More reusable in object-oriented designs due to inheritance and automatic merging.                                   |
| **Usage for Functions**   | Functions can be represented as types, e.g., `type Add = (a: number, b: number) => number;`.           | Functions can also be defined in interfaces but are more common in `type`.                                           |

#### readonly and optional.
* If readonly value is an array then it will allow to push values into it.
* 

```
type User = {
    readonly _id: string;
    name: string;
    email: string;
    isActive: boolean;
    creditDetails?: string;
}

let newUser: User = {
    _id : "3432",
    name: "s",
    email: "s@s.com",
    isActive: false,
//    creditDetails : "kdhfdhf"  // optional
}
newUser.name = "suraj"
newUser._id = "37493874" // will give error
```

#### Union Types
A **union type** allows a variable to hold more than one type.

Syntax: `let variableName: Type1 | Type2 | Type3;`
```
let value: string | number; 
value = "Hello"; // valid 
value = 42; // also valid
```

union in type aliases:
```
type Car = { make: string; model: string }; 
type Bicycle = { brand: string; gearCount: number }; 

function printVehicle(vehicle: Car | Bicycle) { 
	if ("make" in vehicle) { 
	console.log("Car make:", vehicle.make); 
} else { 
	console.log("Bicycle brand:", vehicle.brand); 
} 
}
```

**unions in arrays**
```
const data: (number | string | boolean)[] = [21, 3, 23, "car", "bike"];

// this is not valid statement (as this means either all numbers or all strings)
const data: number[] | string[] = [21, 3, 23, "car", "bike"];

const anyData: any[] = ["num" ,3434, false, null ,undefined, {name : "Suraj"
}];
```

#### Tuples
* A **tuple** in TypeScript is a special kind of array with a fixed number of elements, where each element can have a specific type. 
* Unlike regular arrays, which can contain any number of elements of the same or mixed types, a tuple has a predetermined structure.
##### Syntax:
`let tupleName: [Type1, Type2, Type3, ...] = [value1, value2, value3, ...];`
##### Example:
`let person: [string, number, boolean] = ["Alice", 25, true];`

##### Destructuring tuples:
```
let point: [number, number] = [10, 20]; 
let [x, y] = point; 
console.log(x); // 10 
console.log(y); // 20
```

##### Optional elements: 
* Only the last element can be optional
```
let data: [string, number?] = ["Alice"];
```

##### Rest element:
* Use the `...` syntax to allow variable-length elements of a specific type.
```
let list: [string, ...number[]] = ["Numbers", 1, 2, 3, 4];
```

##### Problems in tuples
* tuples does not restrict the following methods `push()`, `pop()`, `shift()`, `unshift()`, and `splice()` .

#### Enum
* An **enum** in TypeScript is a special data structure that allows you to define a set of named constants.

##### Syntax:
###### Numeric Enum (default numbering starts from 0): 
```
enum Direction {
  Up,    // 0
  Down,  // 1
  Left,  // 2
  Right  // 3
}

```
String Enum:
```
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT"
}


```

