#### Optional Chaining (`?.`) in JavaScript
- Optional chaining is a feature in JavaScript that allows you to access deeply nested object properties or methods without worrying about whether intermediate properties exist. 
- Or simply, it prevents from accessing a property of an undefined.
- If any part of the chain is `undefined` or `null`, the expression safely evaluates to `undefined` instead of throwing an error.
#### Syntax:
The optional chaining operator (`?.`) is placed before a property, method, or array index.
```
object?.property
object.method?.()
object?.[index]
```

#### Example:
1. Accessing Nested Properties
```
const user = {};
console.log(user.address.city); 
// Error: Cannot read property 'city' of undefined
```
  With optional chaining:
```
const user = {};
console.log(user.address?.city); // Output: undefined
```
2. Calling Methods
```
const user = {};
console.log(user.getName()); 
// Error: user.getName is not a function
```
 With optional chaining:
```
const user = {};
console.log(user.getName?.()); // Output: undefined
```
3. Accessing Array Elements
```
const array = null;
console.log(array?.[0]); // Output: undefined
```