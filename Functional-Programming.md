## Callbacks - Passing functions into another function
```js
const prepareGreenTea = () => 'greenTea';

const prepareBlackTea = () => 'blackTea';

const getTea = (prepareTea, numOfCups) => {
  const teaCups = [];

  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }
  return teaCups;
};

const tea4GreenTeam = getTea(prepareGreenTea, 40);
const tea4BlackTeam = getTea(prepareBlackTea, 40);
```

## Pass Arguments to Avoid External Dependence in a Function
```js
let fixedValue = 4;

function incrementer(value) {
  return value + 1;
}
```
