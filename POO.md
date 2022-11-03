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

## Add Prototype property
```js
function Bird(name) {
  this.name = name;  //own property
}

Bird.prototype.fly = function() {
  console.log("I'm flying!");
};
```

## Extend Constructors to Receive Arguments
```js
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let blackbird = new Bird('Thomas', 'black');
```

## Use Inheritance So You Don't Repeat Yourself
```js
function Animal() { };

Animal.prototype = {
  constructor: Animal, 
  describe: function() {
    console.log("My name is " + this.name);
  }
};

let duck = new Animal();
let beagle = new Animal();
```

## Verify an Object's Constructor with instanceof
```js
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird; //true
```

## Understand the Constructor Property
```js
function Dog(name) {
  this.name = name;
}

let beagle = new Dog();

beagle.constructor === Dog; //true
```

## Reset an Inherited Constructor Property
```js
function Animal() { }
function Bird() { }

Bird.prototype = Object.create(Animal.prototype);

let duck = new Bird();
duck.constructor //Animal

Bird.prototype.constructor = Bird;
duck.constructor //Bird
```