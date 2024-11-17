#### Problem Statement:
- Accept a specific type value and return with the same type.
#### Definitions
- Generics are a way to create reusable and flexible components in TypeScript that work with multiple data types. 
- They provide a way to define the type of variables, functions, or classes without specifying the exact type upfront. Instead, the type is determined when the component is used.

#### Basic Syntax
- Generics are defined using **type parameters**, typically represented by letters like `T`, `U`, or `K`. 
- These placeholders are replaced with specific types when the component is used.
```
function identity<T>(value: T): T {
  return value;
}

const numberValue = identity<number>(42); // T is number
const stringValue = identity<string>("Hello"); // T is string

```

```
function wrap<V>(value: V): { value: V } {
  return { value };
}

const wrappedNumber = wrap(123); // T is number
const wrappedString = wrap("Hello"); // T is string

```

#### Using custom types:





#### Generic Array
- Generics can be used to define arrays with specific types.

```
function getFirstElement<T>(arr: T[]): T {
  return arr[0];
}

const numbers = [1, 2, 3];
const firstNumber = getFirstElement(numbers); // T is number

const strings = ["a", "b", "c"];
const firstString = getFirstElement(strings); // T is string
```

Accept an array of a specific type and return a value of the same type.
```
function fn4<T>(val: T[]): T{
    return val[3];
}
// T => type
// T[] => T type array
```
Implementation using arrow function:
```
// Here I am accepting an array of type T, and returning a value of type T.
const fn5 = <T>(val: T[]):T => {
    return val[0];
}
```
React tips:
```
const fn6 = <T,>(val: T[]): T=>{
return val[0];
}
// here a commas is placed to specify as a generics and not a react component.
```


#### Generics Class
