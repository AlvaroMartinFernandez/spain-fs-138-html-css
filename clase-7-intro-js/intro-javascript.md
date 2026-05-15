# Introducción a JavaScript para principiantes

JavaScript es el lenguaje de programación que permite dar interactividad y dinamismo a las páginas web.

## ✅ Tipos de variables

Las variables son espacios de memoria donde almacenamos informacion

- `var`: Variable tradicional, su alcance puede ser global o de función.
- `let`: Variable moderna, su alcance es de bloque ({}) y es reasignable.
- `const`: Variable constante, no se puede reasignar y su alcance es de bloque.

```js
var name = "John";
let age = 20;
const PI = 3.14;
```

## ✅ Tipos de datos

La información puede ser de los siguientes tipos:

- `string`: Texto. Ejemplo: "Hello"
- `number`: Número. Ejemplo: 42
- `boolean`: Verdadero o falso. Ejemplo: true
- `undefined`: Variable declarada pero sin valor.
- `null`: Ausencia intencionada de valor.
- `object`: Colección de datos (arrays, objetos).

```js
let text = "Hello";
let number = 10;
let isAdult = true;
let noValue;
let nothing = null;
let person = { name: "Anna", age: 25 };
let list = [1, 2, 3];
```

### ❓ Diferentes formas de escribir string

- **Comillas simples o dobles**

  - Ejemplo:
    ```js
    const message = "Hello";
    const message = "Hello";
    ```

- **Backticks (template literals)**

  - Ejemplo:

    ```js
    const name = "Alvaro";
    const message = `Hello,
    mi name is ${name}`;
    ```

> Recomendación: Para crear cadenas de texto complejas utiliza siempre Backticks

---

## ✅ Operadores

- Aritméticos: `+`, `-`, `*`, `/`, `%`
- Asignación: `=`, `+=`, `-=`, `*=`, `/=`
- Comparación: `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
- Lógicos: `&&`, `||`, `!`

```js
let sum = 2 + 3;
let equal = 5 == "5"; // true
let strictlyEqual = 5 === "5"; // false
let greater = 10 > 5;
let result = true && false; // false
```

### ❓ Diferencias entre comparación estricta y no estricta

- **Comparación no estricta (`==`):**

  - Compara dos valores y los convierte al mismo tipo si son diferentes (coerción de tipos).
  - Ejemplo:
    ```js
    5 == "5"; // true (convierte "5" a número)
    false == 0; // true (convierte false a 0)
    null == undefined; // true
    ```

- **Comparación estricta (`===`):**
  - Compara dos valores sin convertirlos, deben ser del mismo tipo y valor.
  - Ejemplo:
    ```js
    5 === "5"; // false (número vs string)
    false === 0; // false
    null === undefined; // false
    5 === 5; // true
    ```

> Recomendación: Usa siempre la comparación estricta (`===`) para evitar errores inesperados por la conversión automática de tipos.

---

## ✅ Condicionales

- **Sentencia if**

  - Permiten ejecutar código según una condición.

```js
if (age >= 18) {
  console.log("You are an adult");
} else if (age >= 13) {
  console.log("You are a teenager");
} else {
  console.log("You are a minor");
}
```

- **Operador ternario**

  - Es una forma corta de escribir condicionales.

```js
let message = age >= 18 ? "You are an adult" : "You are a minor";
console.log(message);
```

## ✅ Control de flujo

El condicional IF explicado anteriormente seria una control de flujo

### switch

```js
let fruit = "apple";
switch (fruit) {
  case "apple":
    console.log("It's an apple");
    break;
  case "pear":
    console.log("It's a pear");
    break;
  default:
    console.log("It's neither apple nor pear");
}
```

### for

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### while

```js
let counter = 0;
while (counter < 3) {
  console.log(counter);
  counter++;
}
```

### for...in (recorre propiedades de un objeto)

```js
let person = { name: "Anna", age: 25 };
for (let key in person) {
  console.log(key + ": " + person[key]);
}
```

### for...of (recorre elementos de un array)

```js
let list = ["a", "b", "c"];
for (let value of list) {
  console.log(value);
}
```
