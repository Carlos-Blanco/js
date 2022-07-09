# Testing

1 - Unit tests

2 - Integration tests

3 - End to end tests

4 - UI tests


## Arrange-Act-Assert

Arrange-Act-Assert is a great way to structure test cases. It prescribes an order of operations:

Arrange inputs and targets. Arrange steps should set up the test case. Does the test require any objects or special settings? Does it need to prep a database? Does it need to log into a web app? Handle all of these operations at the start of the test.
Act on the target behavior. Act steps should cover the main thing to be tested. This could be calling a function or method, calling a REST API, or interacting with a web page. Keep actions focused on the target behavior.

Assert expected outcomes. Act steps should elicit some sort of response. Assert steps verify the goodness or badness of that response. Sometimes, assertions are as simple as checking numeric or string values. Other times, they may require checking multiple facets of a system. Assertions will ultimately determine if the test passes or fails.

[Source](https://automationpanda.com/2020/07/07/arrange-act-assert-a-pattern-for-writing-good-tests/)

```
test('test obj', () => {
  //arrange...
  var dummyData = { foo: 'bar' };
  var expected = 'the result we want';
 
  //act...
  var result = functionUnderTest(dummyData);
 
  //assert...
  expect(result).to.equal(expected);
});
```

## Assertions / matchers

```
test('test obj', () => {
  const data = { name: 'Carlos' }; // Para testear objetos se usa .toEqual.
  data.lastname = 'Blanco'; // Manipulación del objeto.
  expect(data).toEqual({ name: 'Carlos', lastname: 'Blanco' }); // Espero que el objeto de arriba sea igual a este.
});

test('null', () => {
  const data = null;
  expect(data).toBeNull(); // Un nulo está definido como nulo.
  expect(data).toBeDefined(); // Un definido es otro tipo de dato en JS.
  expect(data).not.toBeUndefined(); // Podemos usar negaciones.
});

test('booleans', () => {
  // Booleanos directos.
  expect(true).toEqual(true);
  expect(false).toEqual(false);
  // Datos considerados como booleanos.
  expect(0).toBeFalsy();
  expect('').toBeFalsy();
  expect(false).toBeFalsy();
  expect(1).toBeTruthy();
});

test('string', () => {
  // Podemos preguntar si coincide una parte arbitraria con la cadena.
  expect('Christoph').toMatch(/stop/);
});

test('list / arrays', () => {
  const numbers = [1, 2, 3, 4];
  // Podemos preguntar si contiene una parte arbitraria con el arreglo.
  expect(numbers).toContain(3);
});
```


```
test('comparing numbers', () => {
  const value = 2 + 2;
  expect(value).toBeGreaterThan(3); // Es mayor a 3?
  expect(value).toBeGreaterThanOrEqual(3.5); // Es mayor o igual a 3.5?
  expect(value).toBeLessThan(5); // Es menor que 5?
  expect(value).toBeLessThanOrEqual(4.5); // Es menor o igual a 4.5?

  // ToBe y toEqual son equivalentes para números.
  expect(value).toBe(4);
  expect(value).toEqual(4);
});

test('comparing float', () => {
  const value = 3.5 + 4.2;
  // Se usa toBeCloseTo para evitar errores por redondeos en numeros quebrados usando toEqual.
  expect(value).toBeCloseTo(7.7);
});

function formComplete() {
  throw new Error('You are not completed the form');
}

test('exception error', () => {
  // Probar si la función arroja error cuando se llama.
  expect(() => formComplete()).toThrow();
  expect(() => formComplete()).toThrow(Error);

  // Podemos usar el texto del error o una parte.
  expect(() => formComplete()).toThrow('You are not completed the form');
  expect(() => formComplete()).toThrow(/not completed/);
});
```


## Setup and Teardown

beforeAll(): se ejecuta antes de todas las pruebas.

beforeEach(): se ejecuta antes de cada prueba.

afterEach(): se ejecuta después de cada prueba.

afterAll(): se ejecuta después de todas las pruebas


## Test Coverage

Es una medida porcentual que indica cuanto falta probar del código que va a ir a producción, cuál ya está probado, cuál no se usa. ISO y la FAA exigen 100% de cobertura, pero en la realidad no es tan así, por ejemplo hacer test a setter y getters puede llegar a ser innecesario, este 100% no garantiza que aparezcan errores ni que sean el mejor set de pruebas.

## Mocking, Stub, doubles

Dummy: Son datos ficticios para llenar información.

Fake: Son objetos que simulan comportamientos o datos; como un usuario ficticio.

Stubs: Son proveedores o APIs de tatos preparados (BD Clima).

Spies: Son como los stubs, pero se dejan espiar su comportamiento, comunicación e invocación.

Mocks: Stubs + Spies, pueden estar pre-programados para enviar las respuestas supuestas.