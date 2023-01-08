# TIPOS
## Tipado
```ts
function addNumbers(x: number, y: number) {
  return x + y;
}

console.log(addNumbers(3, 6));
```

## Tipo booleano
```ts
let flag: boolean;
let yes = true;
let no = false;
```

## Tipos numéricos y BigInteger
```ts
let x: number;
let y = 0;
let z: number = 123.456;
let big: bigint = 100n;
```

## Tipo de cadena
```ts
let s: string;
let empty = "";
let abc = 'abc';

let firstName: string = "Mateo";
let sentence: string = `My name is ${firstName}.
    I am new to TypeScript.`;
console.log(sentence);
```

## El tipo de enumeración
```ts
enum ContractStatus {
     Permanent,
     Temp,
     Apprentice
}

let employeeStatus: ContractStatus = ContractStatus.Temp;
console.log(employeeStatus);
```

## El tipo any
```ts
let randomValue: any = 10;
randomValue = 'Mateo';   // OK
randomValue = true;      // OK
```

## El tipo unknown
```ts
let randomValue: unknown = 10;
randomValue = true;
randomValue = 'Mateo';

console.log(randomValue.name);  // Error: Object is of type unknown
randomValue();                  // Error: Object is of type unknown
randomValue.toUpperCase();      // Error: Object is of type unknown
```

## Aserción de tipos
```ts
(randomValue as string).toUpperCase();

(<string>randomValue).toUpperCase();
```
```ts
let randomValue: unknown = 10;

randomValue = true;
randomValue = 'Mateo';

if (typeof randomValue === "string") {
    console.log((randomValue as string).toUpperCase());    //* Returns MATEO to the console.
} else {
    console.log("Error - A string was expected here.");    //* Returns an error message.
}
```

## Restricciones de tipos
```ts
string        typeof s === "string"
number        typeof n === "number"
boolean       typeof b === "boolean"
undefined     typeof undefined === "undefined"
function      typeof f === "function"
array         Array.isArray(a)
```

## Tipos de unión
```ts
let multiType: number | boolean;
multiType = 20;         //* Valid
multiType = true;       //* Valid
multiType = "twenty";   //* Invalid
```
```ts
function add(x: number | string, y: number | string) {
    if (typeof x === 'number' && typeof y === 'number') {
        return x + y;
    }
    if (typeof x === 'string' && typeof y === 'string') {
        return x.concat(y);
    }
    throw new Error('Parameters must be numbers or strings');
}
console.log(add('one', 'two'));  //* Returns "onetwo"
console.log(add(1, 2));          //* Returns 3
console.log(add('one', 2));      //* Returns error
```

## Tipos de intersección
```ts
interface Employee {
  employeeID: number;
  age: number;
}
interface Manager {
  stockPlan: boolean;
}
type ManagementEmployee = Employee & Manager;
let newManager: ManagementEmployee = {
    employeeID: 12345,
    age: 34,
    stockPlan: true
};
```

## Tipos literales
```ts
type testResult = "pass" | "fail" | "incomplete";
let myResult: testResult;
myResult = "incomplete";    //* Valid
myResult = "pass";          //* Valid
myResult = "failure";       //* Invalid
```
```ts
type dice = 1 | 2 | 3 | 4 | 5 | 6;
let diceRoll: dice;
diceRoll = 1;    //* Valid
diceRoll = 2;    //* Valid
diceRoll = 7;    //* Invalid
```

## Matrices
```ts
let list: number[] = [1, 2, 3];

let list: Array<number> = [1, 2, 3];
```

## Tuplas
```ts
let person1: [string, number] = ['Marcia', 35];

let person1: [string, number] = ['Marcia', 35, true];  // Error

let person1: [string, number] = [35, 'Marcia'];  // Error
```

# INTERFACES

```ts
interface Employee {
    firstName: string;
    lastName: string;
    fullName(): string;
}
```

```ts
let employee: Employee = {
    firstName : "Emil",
    lastName: "Andersson",
    fullName(): string {
        return this.firstName + " " + this.lastName;
    }
}

employee.firstName = 10;  //* Error - Type 'number' is not assignable to type 'string'
```

## Interfaces - Tipos indexables
```ts
interface IceCreamArray {
    [index: number]: string;
}

let myIceCream: IceCreamArray;
myIceCream = ['chocolate', 'vanilla', 'strawberry'];
let myStr: string = myIceCream[0];
console.log(myStr);
```