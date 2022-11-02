## Objeto literal
```js
const persona = {
  name: 'Carlos',
  age: 46,
}

console.log(persona);
```


## Clase POO
```js
function Persona() {
  this.name = 'Carlos',
  this.age = 46
}

const Yo = new Persona()

console.log(Yo)

Yo.hasOwnProperty('age')
```

## Own property vs Prototype property
```js
function Bird(name) {
  this.name = name;  //own property
}

Bird.prototype.numLegs = 2; // prototype property
```