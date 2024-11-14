
#### Parameters
This is not a right way to define parameters.
```
function user({ name: string , gmail : string, ispaid: boolean }){
}
user({ name: "Suraj", gmail: "suraj@suraj.com", ispaid: false });
```
==`Soln1:`== Add Types Outside of Destructuring.
```
function user({ name, gmail, ispaid }: { name: string; gmail: string; ispaid: boolean }) { 
console.log(name, gmail, ispaid); 
}
```
==`Soln2`== : Define a Type or Interface
```
type User = { name: string; gmail: string; ispaid: boolean };

function user({ name, gmail, ispaid }: User) {
  console.log(name, gmail, ispaid);
}

user({ name: "Suraj", gmail: "suraj@suraj.com", ispaid: false });
```

#### Unusual behavior of object 
Passing extra properties during the function call:
```
const createCourse = ({title, price}) => {
}
createCourse({ title: "ReactJs", price: 3243 , duration : 23});
```
when passing an object it is working
```
const obj = { title: "ReactJs", price: 3243 , duration : 23}
const createCourse = ({title, price}) => {
}
createCourse(obj);
```
#### Return an object
==`fn():{}{}`==
```
function createUser(obj: User ) : {} {
    return {username : obj.name.toUpperCase() , email : obj.email.toLowerCase() , isPaid : !obj.isActive}
}
```
==`fn():{name: string; age: number; email: string }{}`==
```
function createUser(): { name: string; age: number; email: string } { 
	return { name: "Alice", age: 30, email: "alice@example.com" }; 
}
```

#### Type Aliases 
Creating a custom data type:
```
type User = {
	name : string,
	email: string,
	isActive: boolean
}
type customData = string | number;

function createUser(user : User){
}
```
