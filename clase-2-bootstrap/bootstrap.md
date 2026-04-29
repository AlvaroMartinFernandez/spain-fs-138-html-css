# Guía básica de Bootstrap para principiantes

Bootstrap es un framework de código abierto que facilita la creación de sitios web modernos y responsivos utilizando HTML, CSS y JavaScript. Es muy popular porque permite diseñar páginas atractivas rápidamente sin necesidad de escribir mucho código desde cero.

## ✅ ¿Qué es Bootstrap?

- [ ] Es un conjunto de herramientas que incluye estilos, componentes y utilidades listas para usar.
- [ ] Permite crear diseños adaptables a móviles, tablets y ordenadores (responsive design).
- [ ] Se utiliza principalmente para acelerar el desarrollo web y mantener un diseño profesional.

## ✅ ¿Por qué usar Bootstrap?

- [ ] Ahorra tiempo y esfuerzo.
- [ ] Garantiza compatibilidad con dispositivos móviles.
- [ ] Ofrece una apariencia profesional sin ser experto en diseño.

## ✅ ¿Cómo se usa Bootstrap?

- [ ] Puedes incluir Bootstrap en tu proyecto añadiendo un enlace CDN en tu archivo HTML:

  ```html
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
    rel="stylesheet"
  />
  ```

  ```html
  <script
    defer
    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
    crossorigin="anonymous"
  ></script>
  ```

- [ ] También puedes descargar los archivos y usarlos localmente.

## ✅ Estructura básica con Bootstrap

- [ ] Un ejemplo de página básica:

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>Bootstrap demo</title>
      <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet"
        integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB"
        crossorigin="anonymous"
      />
    </head>
    <body>
      <h1>Hello, world!</h1>
      <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
        crossorigin="anonymous"
      ></script>
    </body>
  </html>
  ```

## ✅ BreakPoints Bootstrap

| Tamaño de pantalla          | Infix de clase | Ancho mínimo (breakpoint) |
| --------------------------- | -------------- | ------------------------- |
| Extra pequeño (Extra small) | _(none)_       | `<576px`                  |
| Pequeño (Small)             | `sm`           | `≥576px`                  |
| Mediano (Medium)            | `md`           | `≥768px`                  |
| Grande (Large)              | `lg`           | `≥992px`                  |
| Extra grande (Extra large)  | `xl`           | `≥1200px`                 |
| Extra extra grande (XXL)    | `xxl`          | `≥1400px`                 |

## ✅ Utilidades y clases más usadas

- [ ] `container-fluid`:Es siempre de ancho completo, desde el borde izquierdo al derecho de la ventana. No tiene límites.
- [ ] `container`:Tiene anchos fijos y centrados según los breakpoints de Bootstrap,
- [ ] `row`, `col`: Para crear estructuras de cuadrícula (grid system).
- [ ] `text-center`, `text-end`, `text-start`: Para alinear texto.
- [ ] `mt-3`, `mb-2`, `p-4`: Para márgenes y rellenos.
- [ ] `d-flex`, `justify-content-center`: Para usar Flexbox fácilmente.

## ✅ Componentes principales de Bootstrap

- [ ] **Botones:**

  ```html
  <button class="btn btn-primary">Botón principal</button>
  ```

  <iframe 
    srcdoc='
      <!DOCTYPE html>
      <html>
        <head>
          <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          />
        </head>
        <body class = "d-flex justify-content-center align-items-center" style="height:150px;">
          <button class="btn btn-primary">Botón principal</button>
        </body>
      </html>'
  ></iframe>

- [ ] **Alertas:**
  ```html
  <div class="alert alert-success">¡Operación exitosa!</div>
  ```
   <iframe 
    srcdoc='
      <!DOCTYPE html>
      <html>
        <head>
          <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          />
        </head>
        <body class = "d-flex justify-content-center align-items-center" style="height:150px;">
          <div class="alert alert-success">¡Operación exitosa!</div>
        </body>
      </html>'
  ></iframe>
- [ ] **Barra de navegación (Navbar):**

  ```html
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Logo</a>
  </nav>
  ```

- [ ] **Cards (Tarjetas):**

  ```html
  <div class="card" style="width: 18rem;">
    <div class="card-body">
      <h5 class="card-title">Título</h5>
      <p class="card-text">Texto de ejemplo.</p>
    </div>
  </div>
  ```

## ✅ Ejemplo de uso del sistema Grid de Bootstrap

- [ ] El sistema Grid de Bootstrap permite crear diseños responsivos fácilmente usando filas (`row`) y columnas (`col`).
- [ ] Ejemplo básico:

```html
<div class="container">
  <div class="row">
    <div class="col-4">Columna 1</div>
    <div class="col-4">Columna 2</div>
    <div class="col-4">Columna 3</div>
  </div>
</div>
```

 <iframe style="width:100%"
    srcdoc='
      <!DOCTYPE html>
      <html>
        <head>
          <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          />
        </head>
        <body class = "d-flex justify-content-center align-items-center" >
         <div class="container">
  <div class="row border border-success">
    <div class="col-4 border border-danger">Columna1 </div>
    <div class="col-4 border border-danger">Columna2 </div>
    <div class="col-4 border border-danger">Columna3 </div>
  </div>
</div>
        </body>
      </html>'
  ></iframe>

- [ ] Puedes combinar diferentes tamaños para adaptarte a distintos dispositivos:

```html
<div class="container">
  <div class="row">
    <div class="col-md-6 col-lg-4">Columna A</div>
    <div class="col-md-6 col-lg-8">Columna B</div>
  </div>
</div>
```

<iframe style="width:100%"
    srcdoc='
      <!DOCTYPE html>
      <html>
        <head>
          <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          />
        </head>
        <body class = "d-flex justify-content-center align-items-center" >
         <div class="container">
            <div class="row border border-success">
              <div class="col-md-6 col-lg-4 border border-danger">Columna A</div>
            <div class="col-md-6 col-lg-8 border border-danger">Columna B</div>
            </div>
</div>
        </body>
      </html>'
  ></iframe>

- [ ] El sistema Grid es muy flexible y te permite crear diseños complejos de forma sencilla.

## ✅ Sistema de columnas y tipos de pantalla en Bootstrap

- [ ] El sistema Grid de Bootstrap divide la página en 12 columnas. Puedes combinar columnas para sumar hasta 12 en cada fila.
- [ ] Ejemplo: `col-6` ocupa la mitad del ancho (6 de 12 columnas), `col-4` ocupa un tercio, etc.

### Tipos de pantalla (breakpoints)

Bootstrap adapta el diseño según el tamaño de la pantalla usando clases específicas:

- `col-` para móviles (extra small, <576px)
- `col-sm-` para pantallas pequeñas (≥576px)
- `col-md-` para pantallas medianas (≥768px)
- `col-lg-` para pantallas grandes (≥992px)
- `col-xl-` para pantallas extra grandes (≥1200px)
- `col-xxl-` para pantallas muy grandes (≥1400px)

Por ejemplo:

```html
<div class="row">
  <div class="col-12 col-md-6 col-lg-4">Columna adaptable</div>
  <div class="col-12 col-md-6 col-lg-8">Columna adaptable</div>
</div>
```

Esto significa que en móvil cada columna ocupa todo el ancho, en pantallas medianas la mitad, y en grandes 4 y 8 columnas respectivamente.

## ✅ Grid Example: cajas responsivas según el tamaño de pantalla

- [ ] Combinando varias clases `col-*` en un mismo elemento podemos decidir **cuántas cajas se muestran por fila** dependiendo del ancho de la pantalla.
- [ ] En este ejemplo tenemos un `container` con 6 cajas dentro de un `row`. Cada caja cambia su anchura según el breakpoint:

| Breakpoint        | Clase usada | Cajas por fila |
| ----------------- | ----------- | -------------- |
| Móvil (<576px)    | `col-12`    | 1              |
| Small (≥576px)    | `col-sm-6`  | 2              |
| Medium (≥768px)   | `col-md-4`  | 3              |
| Large (≥992px)    | `col-lg-3`  | 4              |
| Extra Large (≥1200px) | `col-xl-2` | 6           |

```html
<div class="container py-5">
  <div class="row g-3">
    <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2">
      <div class="caja">Caja 1</div>
    </div>
    <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2">
      <div class="caja">Caja 2</div>
    </div>
    <!-- ... más cajas ... -->
  </div>
</div>
```

<iframe style="width:100%; height:420px; border:0;"
  srcdoc='
    <!DOCTYPE html>
    <html>
      <head>
        <link
          href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
          rel="stylesheet"
        />
        <style>
          .caja {
            background-color:#0d6efd;
            color:white;
            text-align:center;
            padding:25px 10px;
            border-radius:8px;
            font-weight:bold;
          }
        </style>
      </head>
      <body>
        <div class="container py-4">
          <div class="row g-3">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 1</div></div>
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 2</div></div>
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 3</div></div>
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 4</div></div>
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 5</div></div>
            <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2"><div class="caja">Caja 6</div></div>
          </div>
        </div>
      </body>
    </html>'
></iframe>

- [ ] Puedes ver el ejemplo completo en [grid-example.html](./grid-example.html). Redimensiona la ventana para ver cómo cambia la distribución de las cajas.

Puedes ver más detalles en la documentación oficial de Bootstrap: [Grid system](https://getbootstrap.com/docs/5.3/layout/grid/)

---

¿Quieres aprender más? Visita la documentación oficial: [getbootstrap.com](https://getbootstrap.com/)
