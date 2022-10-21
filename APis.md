# APIs

## Fetch Promises

```js
const URL = 'https://api.thecatapi.com/v1/images/search';

fetch (URL) {
    .then(res => res.json())
    .then(data => {
      const img = document.querySelector('img');
      img.src = data[0].url;
    });
}
```

## Fetch Async Await

```js
const URL = 'https://api.thecatapi.com/v1/images/search';

async function myCat () {
    const res = await fetch(URL);
    const data = await res.json();
    const img = document.querySelector('img');
    img.src = data[0].url;
}
```