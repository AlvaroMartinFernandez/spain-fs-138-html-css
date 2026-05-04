# Formularios en HTML para principiantes

Los formularios permiten a los usuarios enviar información a una página web. Son esenciales para crear registros, búsquedas, comentarios, etc.

## ✅ Estructura básica de un formulario

```html
<form action="/ruta-destino" method="post">
  <!-- Aquí van los campos -->
</form>
```

- `action`: URL a la que se envían los datos.
- `method`: Puede ser `get` o `post`.

## ✅ ¿Qué es un input?

El elemento `<input>` permite al usuario escribir o seleccionar datos. Ejemplo:

```html
<input type="text" name="usuario" />
```

## ✅ Tipos de input más comunes

- `type="text"`: Texto simple
- `type="email"`: Email (valida formato email)
- `type="password"`: Contraseña
- `type="number"`: Números
- `type="tel"`: Linea de texto para telefonos
- `type="date"`: Fecha
- `type="checkbox"`: Casilla de verificación
- `type="radio"`: Botón de opción
- `type="file"`: Subir archivos

## ✅ Propiedad placeholder

- El atributo `placeholder` muestra un texto de ayuda dentro del input:
  ```html
  <input type="text" placeholder="Escribe tu nombre" />
  ```

## ✅ Más atributos útiles en los inputs

- `readonly`: El campo solo se puede leer, no modificar.
  ```html
  <input type="text" value="Solo lectura" readonly />
  ```
- `disabled`: El campo está deshabilitado, no se puede usar ni enviar.
  ```html
  <input type="text" value="Deshabilitado" disabled />
  ```
- `size`: Define el ancho visible del input (en caracteres No funciona con bootstrap).
  ```html
  <input type="text" size="30" />
  ```

## ✅ Validaciones básicas en HTML

- `required`: El campo es obligatorio.
- `minlength` y `maxlength`: Mínimo y máximo de caracteres.
- `pattern`: Expresión regular para validar el formato.

Ejemplo:

```html
<input type="email" required placeholder="ejemplo@email.com" />
```

## ✅ El atributo action en el formulario

- El atributo `action` indica la URL a la que se enviarán los datos del formulario cuando se pulse el botón de enviar.
  ```html
  <form action="/procesar-datos" method="post">
    <!-- campos -->
  </form>
  ```
- Si no se indica, los datos se envían a la misma página.

## ✅ El botón y los evento onsubmit y reset

- El botón para enviar suele ser:
  ```html
  <button type="submit">Enviar</button>
  ```
- El formulario se envía cuando el usuario hace click en el botón. El atributo `onsubmit` permite ejecutar código al enviar (pero no se usa en este ejemplo porque no queremos JavaScript).

> Por norma, el botón de envío debe estar dentro del formulario (`<form>`). Si el botón está fuera, se debe usar el atributo `form` para asociarlo al formulario:

```html
<form id="mi-formulario">
  <!-- campos -->
</form>
<button type="submit" form="mi-formulario">Enviar</button>
```

Así el botón enviará el formulario aunque esté fuera de la etiqueta `<form>`.

- También existe el botón de tipo `reset`, que sirve para limpiar todos los campos del formulario:
  ```html
  <button type="reset">Cancelar</button>
  ```
  Al pulsar este botón, todos los campos del formulario vuelven a su valor inicial.

## ✅ ¿Cómo funcionan action y submit?

- El atributo `action` del formulario indica la URL (dirección web) a la que se enviarán los datos cuando el usuario pulse el botón de enviar (`submit`).
- Cuando el usuario rellena los campos y pulsa el botón de tipo `submit`, el navegador recopila los datos y los envía a la URL indicada en `action` usando el método especificado (`get` o `post`).
- Si el atributo `action` está vacío o no se pone, los datos se envían a la misma página donde está el formulario.

### Ejemplo:

```html
<form action="/procesar-datos" method="post">
  <input type="text" name="usuario" />
  <button type="submit">Enviar</button>
</form>
```

- Al pulsar "Enviar", el navegador manda el valor del campo `usuario` a la ruta `/procesar-datos`.

### ¿Qué ocurre después?

- El servidor recibe los datos y puede procesarlos (por ejemplo, guardar en una base de datos, mostrar un mensaje, etc.).
- Si la URL no existe, el navegador mostrará un error.

> El atributo `submit` no existe en los formularios, sino que es el tipo del botón que inicia el envío de datos.

## ❓ ¿Es lo mismo action que onsubmit?

No, son cosas diferentes:

- **action**: Es un atributo del formulario (`<form>`) que indica la URL a la que se enviarán los datos cuando el usuario pulse el botón de enviar. Es decir, define el destino de los datos.
  ```html
  <form action="/procesar-datos" method="post">
    <!-- campos -->
  </form>
  ```
- **onsubmit**: Es un evento que se ejecuta justo antes de que el formulario se envíe. Se usa para ejecutar código (normalmente JavaScript) antes del envío, por ejemplo, para validar los datos o mostrar un mensaje.
  ```html
  <form onsubmit="return validarFormulario()">
    <!-- campos -->
  </form>
  ```

> En resumen: `action` define a dónde van los datos, `onsubmit` permite ejecutar código antes de enviarlos.

## ✅ Distribuir inputs con Bootstrap Grid

Bootstrap permite organizar los campos en filas y columnas fácilmente:

```html
<form class="container">
  <div class="row mb-3">
    <div class="col-6">
      <input type="text" class="form-control" placeholder="Nombre" required />
    </div>
    <div class="col-6">
      <input type="email" class="form-control" placeholder="Email" required />
    </div>
  </div>
  <div class="row mb-3">
    <div class="col-12">
      <input
        type="password"
        class="form-control"
        placeholder="Contraseña"
        required
      />
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Enviar</button>
</form>
```

<iframe style="width:100% ; heigth:300px"
    srcdoc='
      <!DOCTYPE html>
      <html>
        <head>
          <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          />
        </head>
        <body class = "d-flex justify-content-center align-items-center p-1" >
         <form class="container">
  <div class="row mb-3">
    <div class="col-6">
      <input type="text" class="form-control" placeholder="Nombre" required />
    </div>
    <div class="col-6">
      <input type="email" class="form-control" placeholder="Email" required />
    </div>
  </div>
  <div class="row mb-3">
    <div class="col-12">
      <input
        type="password"
        class="form-control"
        placeholder="Contraseña"
        required
      />
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Enviar</button>
</form>
        </body>
      </html>'
  ></iframe>

- Usa `form-control` para inputs bonitos.
- Usa `row` y `col` para distribuir los campos.
- Puedes combinar columnas para crear formularios responsivos.

Utiliza [bootstrap](hhttps://getbootstrap.com/docs/5.3/forms/layout/) para hacer tus formularios
