# Quiz de Conocimientos sobre CSS

Este quiz evaluará tu comprensión de los conceptos fundamentales y avanzados de CSS vistos en el módulo. Lee cuidadosamente cada pregunta y selecciona la respuesta correcta.

## Instrucciones

- El quiz consta de 20 preguntas de opción múltiple.
- Cada pregunta correcta vale 5 puntos, para un total de 100 puntos.
- No hay penalización por respuestas incorrectas.
- Tiempo recomendado: 30 minutos.

---

### 1. ¿Cuál es la forma correcta de aplicar estilos a un elemento utilizando CSS interno?

a) `<style src="styles.css"></style>`  
b) `<link rel="stylesheet" href="styles.css">`  
c) `<style> body { color: blue; } </style>`  
d) `<css> body { color: blue; } </css>`

### 2. ¿Qué selector CSS seleccionaría todos los elementos `<p>` que son hijos directos de un elemento con la clase "container"?

a) `.container p`  
b) `.container > p`  
c) `.container + p`  
d) `.container ~ p`

### 3. ¿Cuál de las siguientes propiedades NO afecta el modelo de caja de un elemento?

a) `padding`  
b) `margin`  
c) `border`  
d) `color`

### 4. Si tienes los siguientes selectores, ¿cuál tiene mayor especificidad?

a) `#header .nav li a`  
b) `body #header .nav li a:hover`  
c) `header nav ul li a.active`  
d) `[id="header"] nav li a`

### 5. ¿Cuál de las siguientes es una unidad relativa en CSS?

a) `px`  
b) `pt`  
c) `cm`  
d) `em`

### 6. ¿Qué propiedad CSS permite controlar cómo se distribuyen los elementos flexibles dentro de un contenedor cuando hay espacio disponible?

a) `flex-wrap`  
b) `flex-basis`  
c) `justify-content`  
d) `align-items`

### 7. ¿Cuál es el valor inicial de la propiedad `position` en CSS?

a) `relative`  
b) `absolute`  
c) `static`  
d) `fixed`

### 8. ¿Qué hace la pseudo-clase `:nth-child(2n)`?

a) Selecciona el segundo elemento hijo  
b) Selecciona cada elemento que es el segundo hijo de su padre  
c) Selecciona elementos pares (2, 4, 6, etc.)  
d) Selecciona el elemento que tiene exactamente 2 hijos

### 9. ¿Qué significa "cascada" en Hojas de Estilo en Cascada (CSS)?

a) Los estilos fluyen de arriba hacia abajo en el documento  
b) Los estilos se aplican en orden jerárquico, del más general al más específico  
c) Múltiples reglas pueden aplicarse al mismo elemento, y la especificidad determina cuál prevalece  
d) Los estilos se heredan de elementos padres a elementos hijos

### 10. ¿Cuál de las siguientes declaraciones crea una cuadrícula CSS con 3 columnas de igual tamaño?

a) `grid-template-columns: repeat(3, 1fr);`  
b) `grid-template-columns: 3 1fr;`  
c) `grid-template: 3 auto;`  
d) `grid-columns: repeat(3, 1fr);`

### 11. ¿Cuál es la diferencia entre `visibility: hidden` y `display: none`?

a) No hay diferencia, ambos ocultan el elemento  
b) `visibility: hidden` oculta el elemento pero mantiene su espacio, mientras que `display: none` elimina el elemento del flujo  
c) `visibility: hidden` elimina el elemento del DOM, mientras que `display: none` solo lo oculta visualmente  
d) `visibility: hidden` sólo funciona en elementos block, mientras que `display: none` funciona en cualquier elemento

### 12. ¿Qué media query se aplicaría solo a dispositivos con una anchura máxima de 768px?

a) `@media screen and (width: 768px)`  
b) `@media screen or (max-width: 768px)`  
c) `@media screen and (max-width: 768px)`  
d) `@media (min-device-width: 768px)`

### 13. ¿Cuál es la manera correcta de establecer transparencia en un elemento usando CSS?

a) `transparency: 0.5;`  
b) `opacity: 50%;`  
c) `opacity: 0.5;`  
d) `alpha: 50%;`

### 14. ¿Qué propiedad CSS3 se utilizaría para crear una transición suave cuando un elemento cambia de color al pasar el mouse?

a) `animation: color 1s;`  
b) `transform: color 1s;`  
c) `transition: color 1s;`  
d) `color-change: smooth 1s;`

### 15. En Flexbox, si quieres que los elementos se envuelvan a la siguiente línea cuando no hay suficiente espacio, ¿qué propiedad debes usar?

a) `flex-wrap: wrap;`  
b) `flex-flow: wrap;`  
c) `flex-direction: wrap;`  
d) `flex: wrap;`

### 16. ¿Cuál es el propósito principal de la metodología BEM en CSS?

a) Optimizar el rendimiento del CSS  
b) Crear animaciones más eficientes  
c) Proporcionar una estructura para nombrar clases y organizar el código  
d) Minimizar el uso de media queries

### 17. ¿Cuál de las siguientes opciones representa correctamente una variable CSS (custom property)?

a) `$primary-color: #333;`  
b) `@primary-color: #333;`  
c) `:root { --primary-color: #333; }`  
d) `var primary-color = #333;`

### 18. ¿Qué sucede si aplicas `box-sizing: border-box` a un elemento?

a) El padding y el borde se añaden al ancho y alto especificados  
b) El padding y el borde se incluyen dentro del ancho y alto especificados  
c) Solo el borde se incluye en el ancho y alto especificados  
d) Solo el padding se incluye en el ancho y alto especificados

### 19. ¿Qué hace la siguiente declaración CSS? `img { max-width: 100%; height: auto; }`

a) Estira la imagen al 100% del ancho de su contenedor  
b) Hace que la imagen sea responsive, sin exceder su tamaño original  
c) Recorta la imagen para que siempre ocupe el 100% del ancho  
d) Fuerza a la imagen a tener un ancho del 100% y altura proporcional

### 20. En el contexto de CSS Grid, ¿qué hace la propiedad `grid-area`?

a) Define el área total que ocupará la cuadrícula  
b) Establece el tamaño de las celdas de la cuadrícula  
c) Permite asignar un nombre a un elemento para posicionarlo en la cuadrícula  
d) Determina cuántas áreas tendrá la cuadrícula

---

## Respuestas correctas (para el instructor)

1. c
2. b
3. d
4. b
5. d
6. c
7. c
8. c
9. c
10. a
11. b
12. c
13. c
14. c
15. a
16. c
17. c
18. b
19. b
20. c 