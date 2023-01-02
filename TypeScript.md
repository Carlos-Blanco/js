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

## Los tipos void, null y undefined
```ts

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
string	      typeof s === "string"
number	      typeof n === "number"
boolean	      typeof b === "boolean"
undefined	    typeof undefined === "undefined"
function	    typeof f === "function"
array	        Array.isArray(a)
```