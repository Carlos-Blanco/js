# classList

## Add
```js
const card = document.querySelector("card");

card.classList.add("selected");
card.classList.add("selected", "card--big");
```

## Remove
```js
const card = document.querySelector("card");

card.classList.remove("selected");
```

## Toggle
```js
const card = document.querySelector("card");

card.classList.toggle("selected");
card.classList.toggle("visible", i < 10 ); // toggle class if i < 10
```

## Replace
```js
const card = document.querySelector("card");

card.classList.replace("card", "card-variant");
```

## Item (return the class in the position)
```js
const card = document.querySelector("card");

card.classList.item(0); // return card
```

## Contains
```js
const card = document.querySelector("card");

card.classList.contains("card"); // return true
```

## forEach
```js
const array1 = ['a', 'b', 'c'];

array1.forEach(element => console.log(element));
```