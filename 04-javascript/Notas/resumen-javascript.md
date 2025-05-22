# Resumen del Módulo de JavaScript

## Conceptos Fundamentales

### ¿Qué es JavaScript?
JavaScript es un lenguaje de programación interpretado, de alto nivel, que se utiliza principalmente para crear páginas web interactivas. Permite agregar comportamiento dinámico a las páginas HTML y manipular el DOM (Document Object Model).

### Características principales
- **Interpretado**: Se ejecuta directamente sin necesidad de compilación previa.
- **Dinámico**: El tipo de las variables se determina en tiempo de ejecución.
- **Orientado a objetos**: Utiliza objetos para representar y manipular datos.
- **Basado en prototipos**: La herencia se realiza a través de prototipos, no clases (aunque ES6 introdujo sintaxis de clases).
- **Funciones de primera clase**: Las funciones son objetos que pueden ser pasados como argumentos, retornados y asignados a variables.
- **Single-threaded**: Ejecuta una operación a la vez en un solo hilo.
- **Event-driven**: La ejecución está determinada por eventos como clics o entradas del usuario.

## Sintaxis Básica

### Inserción de JavaScript en HTML
```html
<!-- Interno -->
<script>
    // Código JavaScript aquí
</script>

<!-- Externo -->
<script src="mi-script.js"></script>
```

### Comentarios
```javascript
// Comentario de una línea

/*
  Comentario
  multilínea
*/
```

## Variables y Tipos de Datos

### Declaración de Variables
```javascript
// ES5 y anteriores
var nombre = "Carlos";

// ES6+
let edad = 25;          // Puede cambiar de valor
const PI = 3.1416;      // No puede cambiar de valor
```

### Tipos de Datos Primitivos
- **String**: Cadenas de texto (`"Hola"`, `'Mundo'`, `` `Template literal` ``)
- **Number**: Números (`42`, `3.14`, `NaN`, `Infinity`)
- **Boolean**: Valores lógicos (`true`, `false`)
- **Undefined**: Variable declarada pero sin valor asignado
- **Null**: Valor nulo (ausencia intencional de valor)
- **Symbol**: Identificador único (ES6)
- **BigInt**: Números enteros grandes (ES11)

### Tipos de Datos Compuestos
- **Object**: Colección de propiedades (`{nombre: "Ana", edad: 30}`)
- **Array**: Lista ordenada de valores (`[1, 2, 3, 4]`)
- **Function**: Bloque de código reutilizable
- **Date**: Fecha y hora
- **RegExp**: Expresiones regulares

### Coerción y Conversión de Tipos
```javascript
// Conversión explícita
Number("42");         // 42
String(42);           // "42"
Boolean(1);           // true

// Coerción implícita
"42" + 1;             // "421" (string)
"42" - 1;             // 41 (number)
"42" * 2;             // 84 (number)
```

## Operadores

### Operadores Aritméticos
```javascript
let a = 10, b = 3;

a + b;      // 13 (suma)
a - b;      // 7 (resta)
a * b;      // 30 (multiplicación)
a / b;      // 3.33... (división)
a % b;      // 1 (módulo/resto)
a ** b;     // 1000 (exponenciación ES7)
a++;        // incremento
b--;        // decremento
```

### Operadores de Asignación
```javascript
let x = 5;

x += 3;     // x = x + 3
x -= 2;     // x = x - 2
x *= 4;     // x = x * 4
x /= 2;     // x = x / 2
x %= 3;     // x = x % 3
```

### Operadores de Comparación
```javascript
let a = 5, b = "5";

a == b;     // true (igual en valor)
a === b;    // false (igual en valor y tipo)
a != b;     // false (diferente en valor)
a !== b;    // true (diferente en valor o tipo)
a > 3;      // true (mayor que)
a < 10;     // true (menor que)
a >= 5;     // true (mayor o igual que)
a <= 5;     // true (menor o igual que)
```

### Operadores Lógicos
```javascript
let x = true, y = false;

x && y;     // false (AND lógico)
x || y;     // true (OR lógico)
!x;         // false (NOT lógico)

// Cortocircuito
x && expresion;  // evalúa expresion solo si x es true
y || expresion;  // evalúa expresion solo si y es false
```

## Estructuras de Control

### Condicionales
```javascript
// if, else if, else
if (condicion1) {
    // código si condicion1 es true
} else if (condicion2) {
    // código si condicion2 es true
} else {
    // código si ninguna condición es true
}

// Operador ternario
let resultado = condicion ? valorSiTrue : valorSiFalse;

// switch
switch (expresion) {
    case valor1:
        // código
        break;
    case valor2:
        // código
        break;
    default:
        // código por defecto
}
```

### Bucles
```javascript
// for
for (let i = 0; i < 5; i++) {
    // código que se repite
}

// for...in (para objetos)
for (let propiedad in objeto) {
    // propiedad contiene el nombre de cada propiedad
}

// for...of (para iterables, ES6)
for (let elemento of iterable) {
    // elemento contiene cada valor del iterable
}

// while
while (condicion) {
    // código que se repite mientras la condición sea true
}

// do...while
do {
    // código que se ejecuta al menos una vez
} while (condicion);
```

### Control de Bucles
```javascript
// break - sale del bucle
for (let i = 0; i < 10; i++) {
    if (i === 5) break;
    // sale cuando i es 5
}

// continue - salta a la siguiente iteración
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) continue;
    // solo procesa números impares
}
```

## Funciones

### Declaración de Funciones
```javascript
// Declaración de función
function saludar(nombre) {
    return "Hola " + nombre;
}

// Expresión de función
const saludar = function(nombre) {
    return "Hola " + nombre;
};

// Función flecha (ES6)
const saludar = (nombre) => {
    return "Hola " + nombre;
};

// Función flecha simplificada
const saludar = nombre => "Hola " + nombre;
```

### Parámetros
```javascript
// Parámetros por defecto (ES6)
function saludar(nombre = "Invitado") {
    return "Hola " + nombre;
}

// Parámetros rest (ES6)
function sumar(...numeros) {
    return numeros.reduce((total, num) => total + num, 0);
}

// Desestructuración (ES6)
function procesar({nombre, edad}) {
    return `${nombre} tiene ${edad} años`;
}
```

### Ámbito (Scope)
```javascript
let global = "variable global";

function ejemplo() {
    let local = "variable local";
    console.log(global);  // Accesible
    console.log(local);   // Accesible
}

console.log(global);  // Accesible
console.log(local);   // Error: no definida
```

## Arrays

### Creación y Acceso
```javascript
// Crear array
let frutas = ["manzana", "banana", "naranja"];

// Acceder a elementos
frutas[0];  // "manzana"
frutas[1];  // "banana"

// Propiedades
frutas.length;  // 3
```

### Métodos Importantes
```javascript
// Añadir/quitar elementos
frutas.push("pera");           // Añade al final
frutas.pop();                  // Quita del final
frutas.unshift("fresa");       // Añade al inicio
frutas.shift();                // Quita del inicio
frutas.splice(1, 2, "kiwi");   // Reemplaza elementos

// Buscar elementos
frutas.indexOf("banana");      // Índice o -1
frutas.includes("manzana");    // true o false

// Transformación
let numeros = [1, 2, 3, 4];
numeros.map(n => n * 2);        // [2, 4, 6, 8]
numeros.filter(n => n > 2);     // [3, 4]
numeros.reduce((sum, n) => sum + n, 0);  // 10

// Otros métodos
frutas.join(", ");             // "manzana, banana, naranja"
frutas.slice(1, 3);            // ["banana", "naranja"]
frutas.concat(["uva", "pera"]); // Concatena arrays
```

## Objetos

### Creación y Acceso
```javascript
// Crear objeto literal
let persona = {
    nombre: "Ana",
    edad: 28,
    saludar: function() {
        return "Hola, soy " + this.nombre;
    }
};

// Acceder a propiedades
persona.nombre;        // "Ana"
persona["edad"];       // 28
persona.saludar();     // "Hola, soy Ana"
```

### Métodos de Objetos
```javascript
// Obtener claves y valores
Object.keys(persona);         // ["nombre", "edad", "saludar"]
Object.values(persona);       // ["Ana", 28, ƒ]
Object.entries(persona);      // [["nombre", "Ana"], ["edad", 28], ["saludar", ƒ]]

// Clonar objeto (shallow copy)
let copia = Object.assign({}, persona);
let copia2 = {...persona};  // Spread operator (ES6)
```

## Manejo de Errores

### try/catch/finally
```javascript
try {
    // Código que puede causar un error
    let resultado = dividir(10, 0);
} catch (error) {
    // Manejo del error
    console.error("Ocurrió un error:", error.message);
} finally {
    // Código que se ejecuta siempre, haya error o no
    console.log("Proceso finalizado");
}
```

### Lanzar Errores
```javascript
function dividir(a, b) {
    if (b === 0) {
        throw new Error("No se puede dividir por cero");
    }
    return a / b;
}
```

## ES6+ Características Modernas

### Template Literals
```javascript
let nombre = "María";
let mensaje = `Hola ${nombre}, bienvenida!`;
```

### Destructuring
```javascript
// Arrays
let [a, b] = [1, 2];

// Objetos
let {nombre, edad} = persona;
```

### Spread Operator
```javascript
// Arrays
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];  // [1, 2, 3, 4, 5]

// Objetos
let obj1 = {a: 1, b: 2};
let obj2 = {...obj1, c: 3};  // {a: 1, b: 2, c: 3}
```

### Clases
```javascript
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    saludar() {
        return `Hola, soy ${this.nombre}`;
    }
    
    static crear(nombre, edad) {
        return new Persona(nombre, edad);
    }
}

// Herencia
class Estudiante extends Persona {
    constructor(nombre, edad, curso) {
        super(nombre, edad);
        this.curso = curso;
    }
}
```

### Promesas
```javascript
let promesa = new Promise((resolve, reject) => {
    // Operación asíncrona
    if (exito) {
        resolve(resultado);
    } else {
        reject(error);
    }
});

promesa
    .then(resultado => {
        // Manejo del resultado exitoso
    })
    .catch(error => {
        // Manejo del error
    });
```

### Async/Await
```javascript
async function obtenerDatos() {
    try {
        let respuesta = await fetch('https://api.ejemplo.com/datos');
        let datos = await respuesta.json();
        return datos;
    } catch (error) {
        console.error("Error al obtener datos:", error);
    }
}
```

### Módulos
```javascript
// Exportar
export function saludar(nombre) {
    return `Hola ${nombre}`;
}

export const PI = 3.1416;

export default class Calculadora {
    // ...
}

// Importar
import {saludar, PI} from './utils.js';
import Calculadora from './calculadora.js';
```

## DOM (Document Object Model)

### Selección de Elementos
```javascript
// Seleccionar un elemento
document.getElementById('miElemento');
document.querySelector('.miClase');
document.querySelector('#miId');

// Seleccionar múltiples elementos
document.getElementsByClassName('miClase');
document.getElementsByTagName('div');
document.querySelectorAll('.miClase');
```

### Manipulación del DOM
```javascript
// Crear elementos
let div = document.createElement('div');
div.className = 'contenedor';
div.innerHTML = '<p>Contenido</p>';

// Añadir a la página
document.body.appendChild(div);
elementoPadre.insertBefore(div, elementoReferencia);

// Eliminar elementos
elemento.remove();
elementoPadre.removeChild(elemento);

// Modificar elementos
elemento.textContent = 'Nuevo texto';
elemento.innerHTML = '<strong>HTML</strong>';
elemento.style.color = 'red';
elemento.setAttribute('data-id', '123');
elemento.classList.add('destacado');
elemento.classList.remove('oculto');
elemento.classList.toggle('activo');
```

### Eventos
```javascript
// Asignar evento con addEventListener
elemento.addEventListener('click', function(evento) {
    console.log('Elemento clickeado', evento);
});

// Función de manejador separada
function manejarClick(evento) {
    evento.preventDefault();  // Prevenir comportamiento predeterminado
    evento.stopPropagation(); // Detener propagación del evento
    console.log('Click en', evento.target);
}
elemento.addEventListener('click', manejarClick);

// Remover evento
elemento.removeEventListener('click', manejarClick);
```

## AJAX y Fetch API

### XMLHttpRequest
```javascript
let xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.ejemplo.com/datos', true);
xhr.onreadystatechange = function() {
    if (xhr.readyState === 4 && xhr.status === 200) {
        let datos = JSON.parse(xhr.responseText);
        console.log(datos);
    }
};
xhr.send();
```

### Fetch API (moderno)
```javascript
fetch('https://api.ejemplo.com/datos')
    .then(response => {
        if (!response.ok) {
            throw new Error('Error en la solicitud');
        }
        return response.json();
    })
    .then(datos => {
        console.log(datos);
    })
    .catch(error => {
        console.error('Error:', error);
    });

// Con async/await
async function obtenerDatos() {
    try {
        let response = await fetch('https://api.ejemplo.com/datos');
        if (!response.ok) {
            throw new Error('Error en la solicitud');
        }
        let datos = await response.json();
        console.log(datos);
    } catch (error) {
        console.error('Error:', error);
    }
}
```

## LocalStorage y SessionStorage

### LocalStorage
```javascript
// Guardar datos
localStorage.setItem('nombre', 'Ana');

// Obtener datos
let nombre = localStorage.getItem('nombre');

// Eliminar un item
localStorage.removeItem('nombre');

// Limpiar todo
localStorage.clear();
```

### SessionStorage
```javascript
// Funciona igual que localStorage pero solo dura la sesión
sessionStorage.setItem('token', '123abc');
```

## JSON

### Conversión
```javascript
// Objeto a string JSON
let persona = {nombre: "Juan", edad: 30};
let jsonString = JSON.stringify(persona);

// String JSON a objeto
let jsonData = '{"nombre":"Juan","edad":30}';
let objeto = JSON.parse(jsonData);
```

## Buenas Prácticas

1. **Usar let/const en lugar de var** para evitar problemas de ámbito.
2. **Siempre usar punto y coma (;)** al final de las sentencias.
3. **Evitar variables globales** para prevenir colisiones de nombres.
4. **Usar estrictamente === y !==** en lugar de == y !=.
5. **Manejar errores con try/catch** en operaciones propensas a fallos.
6. **Comentar el código** para explicar partes complejas.
7. **Usar nombres descriptivos** para variables y funciones.
8. **Evitar funciones demasiado largas**, dividir en funciones más pequeñas.
9. **Utilizar el modo estricto** con `"use strict";` al inicio del script.
10. **Validar entradas de usuario** antes de procesarlas.
11. **Evitar modificar objetos o prototipos nativos** de JavaScript.
12. **Optimizar manipulaciones del DOM** agrupando cambios.
13. **Usar promesas o async/await** para código asíncrono en lugar de callbacks anidados.
14. **Realizar pruebas unitarias** de las funciones principales.

## Herramientas de Desarrollo

1. **Console API**
   - `console.log()` - Mensajes informativos
   - `console.error()` - Errores
   - `console.warn()` - Advertencias
   - `console.table()` - Muestra datos en formato de tabla

2. **Debugging**
   - `debugger;` - Punto de interrupción en el código
   - DevTools del navegador (F12 o Ctrl+Shift+I)

## Recursos Recomendados

1. [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/JavaScript) - Documentación completa
2. [JavaScript.info](https://javascript.info/) - Tutorial moderno
3. [Can I Use](https://caniuse.com/) - Compatibilidad de características
4. [ESLint](https://eslint.org/) - Herramienta de análisis de código
5. [Babel](https://babeljs.io/) - Compilador para usar JavaScript moderno 