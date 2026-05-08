# Introducción a Git y GitHub

Git es un sistema de control de versiones que permite guardar el historial de cambios de tus archivos y trabajar en equipo de forma organizada. GitHub es una plataforma online donde puedes alojar tus proyectos Git y colaborar con otras personas.

## ✅ ¿Para qué sirve Git?

- Guardar versiones de tu código.
- Volver a estados anteriores si cometes errores.
- Trabajar en equipo sin pisar el trabajo de otros.
- Probar nuevas ideas en ramas separadas.

## ✅ Comandos principales de Git

- `git init` — Inicia un repositorio Git en una carpeta.
- `git status` — Muestra el estado de los archivos (cambios, sin guardar, etc).
- `git add archivo` — Añade archivos al área de preparación (staging).
- `git commit -m "mensaje"` — Guarda los cambios en el historial.
- `git log` — Muestra el historial de commits.
- `git diff` — Muestra las diferencias entre archivos modificados.
- `git branch` — Lista las ramas existentes.
- `git checkout nombre` — Cambia a esa rama.
- `git checkout -b nombre` — Crea y cambia a una nueva rama en un solo paso.
- `git merge nombre` — Une la rama con la actual.
- `git pull` — Descarga cambios de GitHub y los fusiona con tu rama actual.
- `git push origin rama` — Sube tus cambios a GitHub en la rama especificada.

## ✅ ¿Qué es una rama (branch)?

Una rama es una línea de trabajo independiente. Permite desarrollar nuevas funciones o corregir errores sin afectar el código principal.

- `git branch nombre` — Crea una nueva rama.
- `git checkout nombre` — Cambia a esa rama.
- `git checkout -b nombre` — Crea y cambia a una nueva rama en un solo paso.
- `git merge nombre` — Une la rama con la actual.

## ✅ ¿Qué es un remoto y cómo funciona GitHub?

- Un remoto es una versión del repositorio que está alojada en otro lugar, normalmente en la nube (por ejemplo, GitHub).
- Para conectar tu repositorio local con GitHub, usas:
  ```bash
  git remote add origin https://github.com/usuario/repositorio.git
  ```
- Para subir tus cambios a GitHub:
  ```bash
  git push origin main
  ```
- Para descargar y fusionar los cambios de GitHub a tu rama local:
  ```bash
  git pull origin main
  ```

### Esquema de git pull:

```
[GitHub (remoto)]
      ↓ git pull
[Tu repositorio local]
```

- git pull descarga los cambios del remoto y los fusiona automáticamente con tu rama actual.

### Esquema de git merge:

```
[main] ←─── merge ─── [rama-nueva]
   │                    │
   └───────┬────────────┘
           ↓
     [main actualizado]
```

- git merge toma los cambios de otra rama y los integra en la rama actual.

## ✅ Ejemplo completo de flujo de trabajo

```bash
# Inicializa el repositorio
$ git init
# Añade archivos
$ git add .
# Haz un commit
$ git commit -m "Primer commit"
# Crea y cambia a una rama nueva
$ git checkout -b nueva-funcionalidad
# Haz cambios y guárdalos
$ git add archivo.txt
$ git commit -m "Agrega nueva funcionalidad"
# Vuelve a main y une los cambios
$ git checkout main
$ git merge nueva-funcionalidad
# Sube los cambios a GitHub
$ git push origin main
```

## ✅ Conflictos y cómo solucionarlos

Un conflicto ocurre cuando dos personas modifican la misma parte de un archivo en ramas diferentes y luego intentan unirlas (merge).

### ¿Cómo se ve un conflicto?

El archivo mostrará algo así:

```
<<<<<<< HEAD
Tu versión del código
=======
La otra versión del código
>>>>>>> rama-externa
```

### ¿Cómo solucionarlo?

1. Abre el archivo y elige qué parte del código quieres dejar (puedes combinar ambas si lo necesitas).
2. Borra las líneas `<<<<<<<`, `=======` y `>>>>>>>`.
3. Guarda el archivo.
4. Añade el archivo resuelto con `git add archivo`.
5. Finaliza el merge con `git commit`.

## ✅ Borrar el último commit

- Si quieres borrar el último commit pero mantener los cambios en tu carpeta de trabajo:
  ```bash
  git reset --soft HEAD~1
  ```
- Si quieres borrar el último commit y también los cambios:
  ```bash
  git reset --hard HEAD~1
  ```

## ✅ ¿Qué es HEAD en Git? (explicación detallada)

- `HEAD` es un puntero especial que indica el commit actual en el que estás trabajando y la rama activa.
- Siempre que haces un commit, `HEAD` avanza al nuevo commit.
- Cuando cambias de rama, `HEAD` apunta al último commit de esa rama.

### ¿Cómo visualizar HEAD?

- Usa `git log --oneline --decorate` para ver en qué commit está HEAD y las ramas:
  ```bash
  git log --oneline --decorate
  ```
  Verás algo como:
  ```
  a1b2c3d (HEAD -> main, origin/main) Mensaje del último commit
  ...
  ```
- También puedes ver el contenido del archivo especial HEAD:
  ```bash
  cat .git/HEAD
  ```
  Esto mostrará a qué rama o commit apunta HEAD.

### ¿Cómo mover HEAD entre commits?

- Para moverte a un commit anterior sin cambiar la rama (modo detached HEAD):
  ```bash
  git checkout <hash-del-commit>
  ```
  Ahora HEAD apunta a ese commit y no a una rama.
- Para volver a la rama principal:
  ```bash
  git checkout main
  ```
- También puedes usar `git reset` para mover HEAD y la rama:
  - `git reset --soft <hash>`: Mueve HEAD y la rama, pero mantiene los cambios en staging.
  - `git reset --hard <hash>`: Mueve HEAD y la rama, y descarta todos los cambios posteriores.

### Esquema visual de HEAD:

```
main:   A---B---C (HEAD)
                  ↑
                Tu posición actual

nueva:  A---B---C---D
```

Si haces `git checkout D`, HEAD apunta a D (modo detached HEAD).
Si haces `git checkout main`, HEAD vuelve a apuntar a C en la rama main.

> Recuerda: HEAD es tu “posición actual” en el historial de Git.

## ✅ ¿Cómo ver los hash de los commits?
- Cada commit en Git tiene un identificador único llamado hash (una cadena de números y letras).
- Para ver los hash de los commits, usa:
  ```bash
  git log --oneline
  ```
  Esto mostrará una lista de commits con su hash corto y el mensaje de cada commit:
  ```
  a1b2c3d Mensaje del commit más reciente
  4e5f6g7 Otro mensaje de commit
  ...
  ```
- Si quieres ver el hash completo, usa:
  ```bash
  git log
  ```
  El hash completo aparece al principio de cada commit como `commit 1234567890abcdef...`

## ❓ ¿Qué muestra git log?
- El comando `git log` muestra todos los commits de la rama actual, desde el más reciente hasta el más antiguo.
- Puedes ver el historial completo de cambios realizados en esa rama, no solo el último commit.
- Si quieres ver solo el último commit, puedes usar:
  ```bash
  git log -1
  ```
- También puedes limitar la cantidad de commits mostrados con:
  ```bash
  git log -n 5
  ```
  (esto muestra los 5 últimos commits)

---

Git y GitHub son herramientas fundamentales para cualquier programador. ¡Practica creando ramas, subiendo a remotos y resolviendo conflictos para dominar su uso!
