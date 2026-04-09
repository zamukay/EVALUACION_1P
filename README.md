Universidad Tecnica de Ambato  
FISEI  
Carrera de Software  

**Asignatura:** Manejo y Configuración de Software  
**Nombre del Estudiante:** Anthony Semblantes  
**Fecha:** 08-04-2026

---

# Evaluación Práctica de Git y GitHub

## Instrucciones Generales

- Cada pregunta debe ser respondida directamente en este archivo **(README.md)** debajo del enunciado correspondiente. 
- Es importante que se coloque capturas de pantalla como evidencia de la parte práctica. Se recomienda crear una carpeta `images/` para almacenar las capturas de pantalla.
- Cada respuesta debe ir acompañada de uno o más **commits**, según se indique en cada pregunta.
- Cuando se indique, deberán realizarse acciones prácticas dentro del repositorio (como creación de archivos, ramas, resolución de conflictos, etc.).
- Cada pregunta debe estar **etiquetada con un tag**, únicamente en el commit final correspondiente, con el formato: `"Pregunta 1"`, `"Pregunta 2"`, etc.

---

## Pregunta 1 (1 punto)

**Explicar la diferencia entre los siguientes conceptos/comandos en Git y GitHub:**

- `git clone`  
- `fork`  
- `git pull`

### Parte práctica:

- Realizar un **fork** de este repositorio en la cuenta personal de GitHub del estudiante.
- Luego, realizar un **clone** del fork en el equipo local.
- En este README, describir el proceso seguido:
  - ¿Cómo se realizó el fork?
  - ¿Cómo se realizó el clone del fork?
  - ¿Cómo se verificó que se estaba trabajando sobre el fork y no sobre el repositorio original?
- Realizar en la rama `main` todo lo que corresponde a esta pregunta.

**📝 Respuesta:**

**git clone:** Copia un repositorio remoto completo a tu máquina local.
Crea una carpeta nueva con todos los archivos y el historial de commits.

**fork:** Copia un repositorio ajeno a tu propia cuenta de GitHub.
Se hace desde la web de GitHub y te permite modificar el proyecto
sin afectar el original.

**git pull:** Descarga y fusiona los cambios del repositorio remoto
hacia tu rama local actual. Se usa para mantener tu copia actualizada.

### ¿Cómo se realizó el fork?
Se ingresó al repositorio original en GitHub y se hizo clic en el
botón "Fork" ubicado en la esquina superior derecha. Se seleccionó
la cuenta personal (zamukay) como destino del fork

![Fork en GitHub](images/1.png)

### ¿Cómo se realizó el clone del fork?
Se abrió Git Bash y se ejecutó el siguiente comando:
git clone https://github.com/zamukay/EVALUACION_1P.git

![Fork en GitHub](images/3.png)


### ¿Cómo se verificó que se trabajaba sobre el fork?
Se ejecutó git remote -v dentro de la carpeta clonada.
La URL mostrada apuntaba a la cuenta personal (zamukay) y no
al repositorio del profesor, confirmando que se trabaja sobre el fork.
![Fork en GitHub](images/2.png)


## Pregunta 2 (1 punto)

**Configurar un archivo `.gitignore` para que ignore:**

- Todos los archivos con extensión `.log`.
- Una carpeta llamada `temp/`.
- Todos los archivos `.md` y `.txt`de la carpeta `doc/`. (Probar agregando un archivo `prueba.md` y un archivo `prueba.txt` dentro de la carpeta y fuera de la carpeta.)

### Requisitos:

1. Realizar un **primer commit** que incluya únicamente el archivo `.gitignore` con las reglas de exclusión definidas.
2. Realizar un **segundo commit** que incluya las creación de los archivos de prueba.
2. Realizar un **tercer commit** donde se explique en este README la función del archivo `.gitignore` y se muestre evidencia de que los archivos y carpetas indicadas no están siendo rastreadas por Git.

**Importante:**  
- Solo el **tercer commit** debe llevar el **tag `"Pregunta 2"`**.

**📝 Respuesta:**


## ¿Qué es el .gitignore?
El archivo .gitignore le indica a Git qué archivos o carpetas debe
ignorar y no rastrear. Es útil para excluir archivos temporales,
logs, o cualquier archivo que no deba subirse al repositorio.

![Git status evidencia](images/ignore.png)

## Reglas configuradas
- *.log → ignora todos los archivos con extensión .log
- temp/ → ignora toda la carpeta temp/
- doc/*.md y doc/*.txt → ignora archivos .md y .txt dentro de doc/
![Git status evidencia](images/temp.png.png)

## Evidencia
Los archivos prueba.md y prueba.txt dentro de doc/ no aparecen
en git status, confirmando que están siendo ignorados.
Los mismos archivos fuera de doc/ sí aparecen y son rastreados.

![Git status evidencia](images/evidencia.png)

## Pregunta 3 (2 puntos)

**Utilizar Git Flow para desarrollar una nueva funcionalidad llamada `ingresar-encabezado`.**

### Requisitos:

- Inicializar el repositorio con Git Flow, utilizando las ramas por defecto: `main` y `develop`.
- Crear una rama de tipo `feature` con el nombre `ingresar-encabezado`.
- En dicha rama, **completar con los datos personales del estudiante** el encabezado que ya se encuentra al inicio de este archivo `README.md`.
- Realizar al menos un commit durante el desarrollo.
- Finalizar el hotfix siguiendo el flujo de trabajo establecido por Git Flow.

### En la sección de respuesta, se debe incluir:

- Los **comandos exactos** utilizados desde la inicialización de Git Flow hasta el cierre de la rama.
- Una descripción del **proceso seguido**, indicando el propósito de cada paso.
- Una reflexión sobre las **ventajas de aplicar Git Flow**, especialmente en contextos colaborativos o proyectos de larga duración.

**Importante:**

- Deben realizarse varios commits durante esta pregunta.
- **Solo el commit final** debe llevar el **tag `"Pregunta 3"`**.
- El flujo debe respetar la estructura de Git Flow con las ramas `develop` y `main`.

**📝 Respuesta:**


## Comandos utilizados

1. git flow init → Inicializa Git Flow con ramas main y develop
2. git flow feature start ingresar-encabezado → Crea la rama feature
3. (edición del encabezado)
4. git add README.md → Prepara los cambios
5. git commit → Guarda el progreso
6. git flow feature finish ingresar-encabezado → Fusiona a develop y elimina la rama

## Descripción del proceso
Git Flow organiza el trabajo en ramas especializadas. La rama develop
es la base del desarrollo. Cada nueva funcionalidad se trabaja en una
rama feature separada, y al terminar se fusiona de vuelta a develop.

## Ventajas de Git Flow
- Permite trabajar en varias funcionalidades al mismo tiempo sin conflictos
- Mantiene main siempre estable con código listo para producción
- Facilita el trabajo en equipo porque cada desarrollador trabaja
  en su propia rama sin afectar a los demás
- El historial de commits queda organizado y fácil de entender

![Git Flow init](images/init.png)
![Git Flow init](images/develop.png)
![Feature branch](images/flow.png)
## Pregunta 4 (2 puntos)

**Trabajo con Issues y Pull Requests**

### Parte teórica:

- ¿Qué es un Pull Request y cuál es su función dentro de un flujo de trabajo colaborativo con Git y GitHub?
- ¿Por qué es importante revisar un Pull Request antes de fusionarlo con la rama principal?
- ¿Qué tipo de observaciones o validaciones se suelen realizar durante la revisión de un Pull Request?

### Parte práctica:

- Trabajar en la rama `develop`, ya existente desde la configuración de Git Flow.
- Realizar los cambios necesarios en este archivo `README.md` para responder las preguntas.
- Realizar un **commit** con los cambios de la primera pregunta y subirlo a la rama `develop` del repositorio remoto.
- Crear un **pull request** desde `develop` hacia `main` en GitHub, con el nombre `"Pregunta 4 - Apellido Nombre"`.
- Crear comentarios solicitando: 1. que se agregue la respuesta de la segunda pregunta y luego agregando la respuesta con el respectivo commit; y 2. el mismo procedimiento para la tercera pregunta.
- **Aprobar** el pull request para que se haga el merge respectivo hacia `main`.

### En la sección de respuesta, se debe incluir:

- Un resumen del procedimiento realizado con las respectivas preguntas y capturas.
- El número y enlace al pull request.

**📝 Respuesta:**


## ¿Qué es un Pull Request?
Un Pull Request (PR) es una solicitud para fusionar los cambios de una
rama hacia otra dentro de un repositorio. En un flujo colaborativo,
permite que otros miembros del equipo revisen el código antes de
integrarlo a la rama principal, facilitando la comunicación y el
control de calidad.

![Feature branch](images/push.png)

## ¿Por qué es importante revisar un Pull Request?
Revisar un PR antes de fusionarlo es importante porque permite
detectar errores de código, verificar que se cumplan los estándares
del proyecto, evitar conflictos con otras ramas y garantizar que
los cambios no rompan funcionalidades existentes. Es una práctica
esencial para mantener la calidad del código en equipo.

## ¿Qué observaciones se realizan en la revisión de un PR?
Durante la revisión de un Pull Request se suelen verificar:
- Que el código funcione correctamente y no tenga errores
- Que siga las convenciones y estándares del equipo
- Que los commits tengan mensajes claros y descriptivos
- Que no se incluyan archivos innecesarios
- Que los cambios estén alineados con el objetivo del PR
- Que no genere conflictos con otras ramas o funcionalidades

![PR creado](images/pull.png)
![Comentarios en PR](images/comentario.png)
![Commits en PR](images/commit.png)


## Pregunta 5 (2 puntos)

**Resolver conflictos entre ramas y realizar un Pull Request**

### Requisitos:

- Crear dos ramas llamadas `ramaA` y `ramaB`, ambas a partir de la rama `develop`.
- En `ramaA`, crear un archivo llamado `archivoA.txt` con el contenido:  
  `Contenido A`
- En `ramaB`, crear un archivo con el mismo nombre (`archivoA.txt`), pero con el contenido:  
  `Contenido B`
- Intentar fusionar `ramaB` sobre `ramaA`, lo cual debe generar un conflicto.
- Resolver el conflicto combinando ambos contenidos.
- Realizar el merge de `ramaA` hacia `develop`.
- Crear un **pull request** desde `develop` hacia `main`.
- Una vez completado lo anterior, eliminar las ramas `ramaA` y `ramaB`.

### En la sección de respuesta, se debe incluir:

- El procedimiento completo:
  - Cómo se crearon las ramas.
  - Cómo se generó y resolvió el conflicto.
  - Cómo se realizó el merge hacia `develop`.
  - Cómo se eliminaron las ramas al finalizar.
- El enlace al pull request.
- Una breve explicación de qué es un conflicto en Git y por qué ocurrió en este caso.

**📝 Respuesta:**



## Pregunta 6 (2 puntos)

**Realizar limpieza, explicar versionamiento semántico y enviar cambios al repositorio original**

### Requisitos:

- Trabajar en la rama `develop` del fork del repositorio.
- Eliminar los archivos `archivoA.txt` y `archivoB.txt` creados en preguntas anteriores.
- Realizar un merge desde `develop` hacia `main` en el repositorio local.
- Enviar los cambios de la rama `main` local a la rama `develop` del repositorio remoto (fork). Recuerde incluir todos los tags creados (6 tags).
- Finalmente, crear un **pull request** desde la rama `develop` del fork hacia la rama `main` del repositorio original (del cual se realizó el fork en la Pregunta 1). El titulo del pull request debe ser `"NOMBRE APELLIDOS"`, en la descripción colocar el link de su repositorio de GitHub.

### En la sección de respuesta, se debe incluir:

- Una explicación del proceso realizado paso a paso.
- Una explicación del **versionamiento semántico**, indicando:
  - En qué consiste.
  - Sus tres componentes (MAJOR, MINOR, PATCH).
- Si hace falta agregar alguna evidencia adicional, agregue un tag adicional que sea `Version Final`.

**📝 Respuesta:**

<!-- Escribe aquí tu respuesta completa a la Pregunta 6 -->
