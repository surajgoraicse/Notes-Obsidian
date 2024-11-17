###### Syntax
`const arrayName: dataType[] = [];`
```
const superHero: string[] = [];
superHero.push("superman");
superHero.push("spiderman");

const level: number[] = [1, 2, 3];
level.push(3, 345, 45, 4, 54, 523);

const stringOrNumber: string[]|number[]; //either string or number

const data: (number | string | boolean)[] = [21, 3, 23, "car", "bike"]; // will take number, string and boolean
```

**Array with Generic** 
`const arrayName: Array<dataType> = [];`
```
const superHero: Array<string> = [];
superHero.push("spiderman" , "superman")
superHero.push("choota bheem")

const level: Array<number> = [2,3,23,2,32,4,4454,345];
level.pop()
```

##### An array of arrays
```
const colors: Array<Array<number>> = [[255,255,255] ]
const rgb: number[][] = [[255,255,255]]
```

##### An array of custom data aliases:
```
type User = {
    name: string;
    email: string;
    isActive: boolean;
}
const users: User[] = [{name : "Suraj" , email: "suraj@gorai.com" , isActive: true}]

const employees: Array<User> = [];

```
