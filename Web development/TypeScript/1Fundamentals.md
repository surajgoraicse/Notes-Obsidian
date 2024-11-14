#### Definitions
TypeScript is a development tool which helps to write better code.


#### Types:
1. Primitives : string , numbers and boolean.
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

