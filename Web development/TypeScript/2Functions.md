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

```