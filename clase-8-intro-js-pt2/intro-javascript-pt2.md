## ✅ Funciones

Las funciones permiten agrupar código reutilizable. Puedes definir funciones con o sin parámetros y con o sin valor de retorno.

### Parámetros

Los parámetros son variables que se pasan a la función para que trabaje con diferentes valores. No son obligatorios.

```js
function greet(name) {
  console.log("Hello, " + name);
}
greet("Anna"); // "Hello, Anna"
greet(); // "Hello, undefined" (si no se pasa parámetro)
```

Puedes definir funciones sin parámetros:

```js
function sayHi() {
  console.log("Hi!");
}
sayHi(); // "Hi!"
```

### Valor de retorno (`return`)

El valor de retorno es lo que la función devuelve al ser llamada. No es obligatorio usar `return`.

```js
function sum(a, b) {
  return a + b;
}
let result = sum(2, 3); // result = 5

function showMessage() {
  console.log("This function does not return anything");
}
showMessage(); // Imprime el mensaje, pero no retorna valor
```

Si no se usa `return`, la función devuelve `undefined` por defecto.

### Funciones anidadas

Puedes definir funciones dentro de otras funciones. Esto permite organizar el código y crear funciones auxiliares.

```js
function calculate(a, b) {
  function sum() {
    return a + b;
  }
  function mul() {
    return a * b;
  }
  function diff() {
    return a - b;
  }
  return {
    sum: sum(),
    mul: mul(),
    diff: diff(),
  };
}

const results = calculate(5, 3);
console.log(results); // { sum: 8, mul: 15, diff: 2 }
```

En este ejemplo, `sum`, `mul` y `diff` son funciones anidadas dentro de `calculate` y solo pueden ser usadas dentro de ella.

## ✅ Tipos de funciones en JavaScript

### 1. Funciones clásicas (declaradas)

Son las funciones tradicionales, tienen nombre y pueden ser llamadas en cualquier parte del código (incluso antes de su declaración por el hoisting --> al compilar las declaracion de funciones se eleva).

```js
function greet(name) {
  return "Hello, " + name;
}
console.log(greet("Anna")); // "Hello, Anna"
```

### 2. Funciones anónimas

Son funciones sin nombre, normalmente se asignan a una variable o se usan como argumento en otras funciones.

```js
const sayHi = function (name) {
  return "Hi, " + name;
};
console.log(sayHi("John")); // "Hi, John"
```

### 3. Funciones flecha (arrow functions)

Son una forma más corta de escribir funciones anónimas. No tienen su propio `this` y no pueden ser usadas como constructores.

```js
const add = (a, b) => {
  return a + b;
};
console.log(add(2, 3)); // 5
```

Si la función solo tiene una expresión, puedes omitir las llaves y el return:

```js
const double = (x) => x * 2;
console.log(double(4)); // 8
```

### Ejemplo para entender las diferencias

Supongamos que queremos crear una función que salude y use el contexto `this`:

```js
const person = {
  name: "Anna",
  // Función clásica
  greetClassic: function () {
    return "Hello, " + this.name;
  },
  // Función flecha
  greetArrow: () => {
    return "Hello, " + this.name;
  },
};

console.log(person.greetClassic()); // "Hello, Anna"
console.log(person.greetArrow()); // "Hello, undefined"
```

- En la función clásica, `this` se refiere al objeto `person`.
- En la función flecha, `this` no es el objeto, sino el contexto externo (en este caso, el global), por eso no accede correctamente a `name`.

> Las funciones flecha son ideales para callbacks y funciones cortas, pero no para métodos de objetos donde necesitas acceder a `this`.

### Diferencias principales

- Las funciones clásicas pueden ser llamadas antes de su declaración (hoisting).
- Las funciones anónimas y flecha solo pueden ser usadas después de ser definidas.
- Las funciones flecha no tienen su propio `this`, lo que afecta cómo acceden al contexto en objetos y clases.

---

## ✅ Scope (Ámbito de las variables) en JavaScript

El scope determina desde dónde se puede acceder a una variable. Hay tres tipos principales:

- Scope global: variable accesible desde cualquier parte del código.
- Scope de función: variable accesible solo dentro de la función donde se declara.
- Scope de bloque: variable accesible solo dentro del bloque `{}` donde se declara (con let y const).

### Ejemplo de scope con funciones

```js
let value = "global"; // scope global

function showValue() {
  let value = "local"; // scope local de función
  console.log(value); // "local"
}

showValue();
console.log(value); // "global"
```

### Ejemplo de scope de bloque

```js
if (true) {
  let blockVar = "inside block";
  console.log(blockVar); // "inside block"
}
// console.log(blockVar); // Error: blockVar is not defined
```

### Uso de this para referirse al scope de un objeto

```js
const user = {
  name: "Anna",
  showName: function () {
    console.log(this.name); // "Anna"
  },
  showNameArrow: () => {
    console.log(this.name); // undefined (this no es el objeto)
  },
};

user.showName(); // "Anna"
user.showNameArrow(); // undefined
```

- En una función clásica, `this` se refiere al objeto donde se llama la función.
- En una función flecha, `this` no es el objeto, sino el contexto externo (global).

> Recuerda: El scope y el uso de this son fundamentales para entender cómo funcionan las variables y los objetos en JavaScript.

## ✅ Arrays y objetos en JavaScript

### Arrays

Un array es una lista ordenada de elementos.

```js
let fruits = ["apple", "banana", "orange"];
```

#### Acceso a los miembros de un array y funcionamiento de los índices

- Los arrays almacenan elementos en posiciones llamadas índices.
- El primer elemento está en el índice 0, el segundo en el índice 1, y así sucesivamente.

```js
let fruits = ["apple", "banana", "orange"];
console.log(fruits[0]); // "apple"
console.log(fruits[1]); // "banana"
console.log(fruits[2]); // "orange"
```

#### Métodos importantes de los arrays (explicación detallada):

- `forEach(fn)`: Ejecuta una función para cada elemento del array. No devuelve nada.

  ```js
  fruits.forEach((fruit, index) => {
    console.log(index + ": " + fruit);
  });
  // 0: apple
  // 1: banana
  // 2: orange
  ```

- `map(fn)`: Crea un nuevo array aplicando una función a cada elemento. No modifica el original.

  ```js
  let upperFruits = fruits.map((fruit) => fruit.toUpperCase());
  console.log(upperFruits); // ["APPLE", "BANANA", "ORANGE"]
  ```

- `filter(fn)`: Crea un nuevo array con los elementos que cumplen una condición.

  ```js
  let longFruits = fruits.filter((fruit) => fruit.length > 5);
  console.log(longFruits); // ["banana", "orange"]
  ```

- `find(fn)`: Devuelve el primer elemento que cumple una condición. Si no encuentra ninguno, devuelve undefined.

  ```js
  let found = fruits.find((fruit) => fruit === "banana");
  console.log(found); // "banana"
  ```

- `reduce(fn, initialValue)`: Reduce el array a un solo valor, acumulando el resultado.

  ```js
  let numbers = [1, 2, 3, 4];
  let sum = numbers.reduce((accumulator, current) => {
    return accumulator + current;
  }, 0);
  console.log(sum); // 10

  // Ejemplo más extenso: contar cuántas frutas tienen más de 5 letras
  let count = fruits.reduce((acc, fruit) => {
    return fruit.length > 5 ? acc + 1 : acc;
  }, 0);
  console.log(count); // 2
  ```

- `push(element)`: Añade un elemento al final.
  ```js
  fruits.push("pear"); // ["apple", "banana", "orange", "pear"]
  ```
- `pop()`: Elimina el último elemento.
  ```js
  fruits.pop(); // ["apple", "banana", "orange"]
  ```
- `shift()`: Elimina el primer elemento.
  ```js
  fruits.shift(); // ["banana", "orange"]
  ```
- `unshift(element)`: Añade un elemento al principio.
  ```js
  fruits.unshift("grape"); // ["grape", "banana", "orange"]
  ```

### Objetos

Un objeto es una colección de pares clave-valor.

```js
let person = {
  name: "John",
  age: 30,
  isStudent: false,
};
```

#### Métodos y propiedades importantes de los objetos:

- Acceso a propiedades:
  ```js
  console.log(person.name); // "John"
  console.log(person["age"]); // 30
  ```
- Añadir o modificar propiedades:
  ```js
  person.city = "London";
  person.age = 31;
  ```
- Eliminar propiedades:
  ```js
  delete person.isStudent;
  ```
- Recorrer propiedades:
  ```js
  for (let key in person) {
    console.log(key + ": " + person[key]);
  }
  ```
- Obtener todas las claves:
  ```js
  Object.keys(person); // ["name", "age", "city"]
  ```
- Obtener todos los valores:
  ```js
  Object.values(person); // ["John", 31, "London"]
  ```
- Obtener pares clave-valor:
  ```js
  Object.entries(person); // [["name", "John"], ["age", 31], ["city", "London"]]
  ```

## ✅ Tipos de copias en JavaScript

### Copia por asignación

- Cuando asignas un array u objeto a otra variable, ambas apuntan al mismo lugar en memoria.
- Cambios en una afectan a la otra.

```js
let arr1 = [1, 2, 3];
let arr2 = arr1;
arr2[0] = 99;
console.log(arr1); // [99, 2, 3]
```

### Copia superficial (shallow copy)

- Crea una copia de los elementos, pero si hay objetos dentro, solo copia la referencia.

```js
let arr3 = [...arr1]; // usando spread operator
arr3[1] = 100;
console.log(arr1); // [99, 2, 3]
console.log(arr3); // [99, 100, 3]
```

### Copia profunda (deep copy)

- Crea una copia independiente, incluso de los objetos internos.

```js
let obj1 = { name: "Anna", address: { city: "London" } };
let obj2 = JSON.parse(JSON.stringify(obj1));
obj2.address.city = "Paris";
console.log(obj1.address.city); // "London"
console.log(obj2.address.city); // "Paris"
```

> Resumen:

- Asignación y shallow copy pueden compartir datos internos.
- Deep copy crea una copia totalmente independiente.
