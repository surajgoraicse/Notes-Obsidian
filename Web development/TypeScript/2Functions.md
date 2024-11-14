##### Basic Function Syntax with Types
```
function findSquare(num: number) {
    return num * num;
}
const sq = findSquare(34)

function signUp(name: string , email: string , isPaid: boolean){
}
signUp("Suraj", "suraj@gmail.com", false);

```

##### Passing default values:
```
const login = (name: string , email: string, isPaid:boolean = false) => {
}
login("suraj" , "suraj@gorai.com" )
```

##### Return Type
```
function findSquare(num: number) : number {
    return num * num;
}
const sq = findSquare(343)
console.log(sq);


```

#### void and never
```
function consoleError(error : string):void{
console.log(error)
}
```
The `never` type represents values which are _never_ observed. In a return type, this means that the function ==`throws an exception or terminates`== execution of the program.
```
function fail(msg: string): never {
throw new Error(msg);
}
```