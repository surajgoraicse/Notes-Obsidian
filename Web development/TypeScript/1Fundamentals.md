#### Definitions
TypeScript is a development tool which helps to write better code.


#### Types:
1. Primitives : string , number and boolean.
2. Special Types : any, unknown, void, null, undefined, never.
3. Complex Types : Arrays, Tuples.
4. Object Types : `let user: { name: string; age: number } = { name: "Alice", age: 25 };`
#### Syntax:
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
#### readonly and optional
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