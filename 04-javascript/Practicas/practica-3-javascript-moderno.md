# Práctica 3: JavaScript Moderno (ES6+)

## Objetivo

Practicar las características modernas de JavaScript (ES6+) que son fundamentales para el desarrollo con React. En esta práctica, implementarás diferentes funcionalidades utilizando sintaxis y patrones modernos que te permitirán familiarizarte con el estilo de código utilizado en React.

## Requisitos previos

- Conocimientos básicos de JavaScript
- Conocimientos básicos de HTML y CSS
- Familiaridad con las funciones y estructuras de control en JavaScript

## Instrucciones

Para cada uno de los siguientes ejercicios, crea un archivo HTML separado con el código JavaScript necesario. Utiliza las características modernas de JavaScript (ES6+) para resolver cada problema.

### Ejercicio 1: Arrow Functions y Template Literals

Crea una función que genere un componente de tarjeta de usuario utilizando template literals y arrow functions:

1. Crea una arrow function llamada `crearTarjetaUsuario` que acepte un objeto con las propiedades: `nombre`, `email`, `rol` y `imagenUrl`
2. La función debe retornar un string de HTML utilizando template literals
3. El HTML generado debe mostrar la información del usuario en una tarjeta con estilos básicos
4. Utiliza operadores ternarios para mostrar condicionalmente ciertos elementos (por ejemplo, si el rol es "admin", mostrar un badge especial)
5. Crea un array de usuarios y utiliza `map` con arrow functions para generar múltiples tarjetas

**Ejemplo de uso:**
```javascript
const usuarios = [
  {
    nombre: "Ana Pérez",
    email: "ana@ejemplo.com",
    rol: "admin",
    imagenUrl: "https://randomuser.me/api/portraits/women/1.jpg"
  },
  {
    nombre: "Juan García",
    email: "juan@ejemplo.com",
    rol: "usuario",
    imagenUrl: "https://randomuser.me/api/portraits/men/1.jpg"
  }
];

const tarjetasHTML = usuarios.map(crearTarjetaUsuario).join('');
document.getElementById('contenedor').innerHTML = tarjetasHTML;
```

### Ejercicio 2: Destructuring y Parámetros por Defecto

Implementa un sistema para crear elementos de interfaz con opciones configurables:

1. Crea una función `crearBoton` que utilice parámetros por defecto y destructuring
2. La función debe aceptar un objeto de configuración con propiedades como: `texto`, `color`, `tamaño`, `onClick`, etc.
3. Utiliza el destructuring en los parámetros con valores por defecto para las propiedades
4. La función debe retornar un elemento de botón (puedes usar `document.createElement` o template literals)
5. Crea otra función similar `crearInput` que también utilice destructuring y parámetros por defecto

**Ejemplo de uso:**
```javascript
const botonPrimario = crearBoton({
  texto: 'Guardar',
  color: 'azul',
  onClick: () => alert('Guardado')
});

const inputNombre = crearInput({
  tipo: 'text',
  placeholder: 'Escribe tu nombre',
  requerido: true
});

document.body.appendChild(botonPrimario);
document.body.appendChild(inputNombre);
```

### Ejercicio 3: Spread Operator y Funciones Puras

Implementa un gestor de tareas utilizando principios de inmutabilidad:

1. Crea un array inicial de tareas, donde cada tarea es un objeto con `id`, `texto` y `completada`
2. Implementa las siguientes funciones puras (que no modifican los datos originales):
   - `agregarTarea(tareas, texto)`: retorna un nuevo array con la tarea agregada
   - `eliminarTarea(tareas, id)`: retorna un nuevo array sin la tarea especificada
   - `toggleTarea(tareas, id)`: retorna un nuevo array con la tarea especificada marcada como completada/no completada
   - `filtrarTareas(tareas, filtro)`: retorna un nuevo array con tareas filtradas ("todas", "completadas", "pendientes")
3. Utiliza el spread operator (`...`) para crear nuevos arrays sin modificar los originales
4. Implementa una interfaz simple para probar estas funciones

**Ejemplo de uso:**
```javascript
let tareas = [
  { id: 1, texto: "Aprender JavaScript moderno", completada: true },
  { id: 2, texto: "Practicar Destructuring", completada: false }
];

tareas = agregarTarea(tareas, "Dominar el Spread Operator");
console.log(tareas); // Array con 3 tareas

tareas = toggleTarea(tareas, 2);
console.log(tareas); // La segunda tarea ahora está completada

const tareasPendientes = filtrarTareas(tareas, "pendientes");
console.log(tareasPendientes); // Solo tareas pendientes
```

### Ejercicio 4: Módulos y Async/Await

Crea una aplicación simple que obtenga datos de usuarios de una API y muestre tarjetas de perfil:

1. Crea un archivo `api.js` que exporte funciones para obtener datos de la API JSONPlaceholder
2. Utiliza la sintaxis de módulos ES6 (`import`/`export`)
3. Implementa una función asíncrona `obtenerUsuarios()` utilizando `async/await` y `fetch`
4. Crea un archivo `ui.js` que exporte funciones para construir elementos de UI
5. En tu archivo principal, importa ambos módulos y crea una aplicación que:
   - Obtenga los usuarios de la API
   - Muestre un loading spinner mientras se cargan los datos
   - Renderice tarjetas de usuario una vez que los datos estén disponibles
   - Maneje posibles errores con try/catch

**API a utilizar:** `https://jsonplaceholder.typicode.com/users`

### Ejercicio 5: Proyecto Integrador - Mini Tienda

Crea una mini aplicación de tienda que integre todas las características anteriores:

1. Define un array de productos con sus propiedades (nombre, precio, stock, imagen, etc.)
2. Implementa un estado global de la aplicación (carrito, filtros, etc.)
3. Crea funciones puras para manipular ese estado (añadir al carrito, filtrar productos, etc.)
4. Utiliza todas estas funcionalidades para crear una interfaz de tienda que:
   - Muestre una lista de productos
   - Permita filtrarlos por categoría o precio
   - Permita añadirlos al carrito
   - Muestre el carrito con los productos seleccionados
   - Calcule el total del carrito

Utiliza todas las características de ES6+ que hemos visto:
- Arrow functions
- Template literals
- Destructuring
- Parámetros por defecto
- Spread operator
- Funciones puras
- Map, filter, reduce

## Criterios de evaluación

El ejercicio se considerará completado cuando:

1. Se utilicen correctamente las características modernas de JavaScript
2. Cada función cumpla con el principio de inmutabilidad (no modificar datos originales)
3. El código esté bien organizado y siga buenas prácticas
4. La aplicación funcione correctamente en el navegador
5. Se manejen adecuadamente los posibles errores

## Entrega

Sube tus archivos HTML y JavaScript para cada ejercicio a la plataforma de entrega. Asegúrate de que cada archivo HTML pueda ejecutarse independientemente y muestre el resultado esperado.

## Recursos adicionales

- [Documentación de ES6 - Mozilla Developer Network](https://developer.mozilla.org/es/docs/Web/JavaScript)
- [API JSONPlaceholder](https://jsonplaceholder.typicode.com/)
- [Guía de Arrow Functions](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Guía de Destructuring](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) 