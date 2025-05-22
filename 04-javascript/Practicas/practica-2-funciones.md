# Práctica 2: Funciones en JavaScript

## Objetivos
- Comprender los diferentes tipos de declaración de funciones
- Practicar el uso de parámetros y valores de retorno
- Experimentar con funciones flecha, closures y otros conceptos avanzados
- Aplicar buenas prácticas en el desarrollo de funciones

## Ejercicio 1: Tipos de Declaraciones de Funciones

1. Crea un archivo HTML llamado `practica-funciones.html` con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Funciones en JavaScript</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        .output {
            background-color: #f8f9fa;
            border-left: 4px solid #28a745;
            padding: 15px;
            margin: 15px 0;
        }
        .error {
            background-color: #f8d7da;
            border-left: 4px solid #dc3545;
            color: #721c24;
            padding: 15px;
            margin: 15px 0;
        }
        button {
            padding: 8px 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px;
        }
        button:hover {
            background-color: #0069d9;
        }
    </style>
</head>
<body>
    <h1>Práctica de Funciones en JavaScript</h1>
    
    <h2>Ejercicio 1: Tipos de Declaraciones de Funciones</h2>
    <button onclick="probarFuncionDeclarada()">Función Declarada</button>
    <button onclick="probarFuncionExpresion()">Función Expresión</button>
    <button onclick="probarFuncionFlecha()">Función Flecha</button>
    <div id="output1" class="output"></div>
    
    <h2>Ejercicio 2: Parámetros y Retorno</h2>
    <button onclick="probarParametros()">Probar Parámetros</button>
    <div id="output2" class="output"></div>
    
    <h2>Ejercicio 3: Funciones Avanzadas</h2>
    <button onclick="probarClosure()">Probar Closure</button>
    <button onclick="probarRecursion()">Probar Recursión</button>
    <div id="output3" class="output"></div>
    
    <h2>Ejercicio 4: Calculadora Funcional</h2>
    <div>
        <input type="number" id="num1" placeholder="Número 1">
        <input type="number" id="num2" placeholder="Número 2">
        <div>
            <button onclick="calcular('sumar')">Sumar</button>
            <button onclick="calcular('restar')">Restar</button>
            <button onclick="calcular('multiplicar')">Multiplicar</button>
            <button onclick="calcular('dividir')">Dividir</button>
        </div>
        <div id="resultadoCalc" class="output"></div>
    </div>

    <script src="funciones.js"></script>
</body>
</html>
```

2. Crea un archivo JavaScript llamado `funciones.js` y declara las siguientes funciones:

```javascript
// Declaración de función
function saludarDeclarada(nombre) {
    return `¡Hola, ${nombre}! Soy una función declarada.`;
}

// Expresión de función
const saludarExpresion = function(nombre) {
    return `¡Hola, ${nombre}! Soy una función expresión.`;
};

// Función flecha
const saludarFlecha = (nombre) => {
    return `¡Hola, ${nombre}! Soy una función flecha.`;
};

// Función para probar cada tipo
function probarFuncionDeclarada() {
    const output = document.getElementById('output1');
    output.innerHTML = saludarDeclarada("Estudiante");
}

function probarFuncionExpresion() {
    const output = document.getElementById('output1');
    output.innerHTML = saludarExpresion("Estudiante");
}

function probarFuncionFlecha() {
    const output = document.getElementById('output1');
    output.innerHTML = saludarFlecha("Estudiante");
}
```

3. Comprueba cada tipo de función haciendo clic en los botones correspondientes.

## Ejercicio 2: Parámetros y Retorno

1. Añade al archivo `funciones.js` las siguientes funciones:

```javascript
// Función con parámetros por defecto
function saludarConDefecto(nombre = "Invitado") {
    return `¡Hola, ${nombre}!`;
}

// Función con múltiples parámetros
function presentar(nombre, edad, profesion) {
    return `Soy ${nombre}, tengo ${edad} años y soy ${profesion}.`;
}

// Función con parámetro rest
function sumarTodos(...numeros) {
    return numeros.reduce((total, num) => total + num, 0);
}

// Función con retorno múltiple (usando objeto)
function analizarNumero(numero) {
    return {
        valor: numero,
        esPar: numero % 2 === 0,
        esPositivo: numero > 0,
        doble: numero * 2
    };
}

// Función para probar los parámetros
function probarParametros() {
    const output = document.getElementById('output2');
    
    // Limpiamos el contenido anterior
    output.innerHTML = "";
    
    // Probamos cada función
    const resultados = [
        `<strong>Parámetro por defecto:</strong> ${saludarConDefecto()}`,
        `<strong>Parámetro por defecto con valor:</strong> ${saludarConDefecto("Carlos")}`,
        `<strong>Múltiples parámetros:</strong> ${presentar("Ana", 28, "desarrolladora")}`,
        `<strong>Parámetro rest (3, 5, 7):</strong> ${sumarTodos(3, 5, 7)}`,
        `<strong>Parámetro rest (1 al 10):</strong> ${sumarTodos(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)}`
    ];
    
    // Probamos la función con retorno múltiple
    const analisis = analizarNumero(7);
    resultados.push(
        `<strong>Retorno múltiple (objeto) para el número 7:</strong><br>` +
        `Valor: ${analisis.valor}<br>` +
        `¿Es par? ${analisis.esPar ? "Sí" : "No"}<br>` +
        `¿Es positivo? ${analisis.esPositivo ? "Sí" : "No"}<br>` +
        `Doble: ${analisis.doble}`
    );
    
    // Mostramos los resultados
    output.innerHTML = resultados.join("<br><br>");
}
```

2. Prueba estas funciones haciendo clic en el botón "Probar Parámetros".

## Ejercicio 3: Funciones Avanzadas

1. Añade al archivo `funciones.js` las siguientes funciones:

```javascript
// Closure (contador)
function crearContador() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}

// Instancia de nuestro contador
const contador = crearContador();

// Función recursiva (factorial)
function factorial(n) {
    // Caso base
    if (n <= 1) {
        return 1;
    }
    // Caso recursivo
    return n * factorial(n - 1);
}

// Función para probar closure
function probarClosure() {
    const output = document.getElementById('output3');
    
    output.innerHTML = `
        <strong>Contador (closure):</strong><br>
        Primera llamada: ${contador()}<br>
        Segunda llamada: ${contador()}<br>
        Tercera llamada: ${contador()}
    `;
}

// Función para probar recursión
function probarRecursion() {
    const output = document.getElementById('output3');
    
    const resultados = [
        `<strong>Factorial (recursión):</strong>`,
        `Factorial de 1: ${factorial(1)}`,
        `Factorial de 3: ${factorial(3)}`,
        `Factorial de 5: ${factorial(5)}`,
        `Factorial de 10: ${factorial(10)}`
    ];
    
    output.innerHTML = resultados.join("<br>");
}
```

2. Prueba estas funciones haciendo clic en los botones "Probar Closure" y "Probar Recursión".

## Ejercicio 4: Calculadora Funcional

1. Completa el archivo `funciones.js` con las siguientes funciones para implementar la calculadora:

```javascript
// Funciones puras para operaciones matemáticas
const operaciones = {
    sumar: (a, b) => a + b,
    restar: (a, b) => a - b,
    multiplicar: (a, b) => a * b,
    dividir: (a, b) => b !== 0 ? a / b : "Error: División por cero"
};

// Función de orden superior que recibe y ejecuta otra función
function calcular(operacion) {
    const num1 = parseFloat(document.getElementById('num1').value);
    const num2 = parseFloat(document.getElementById('num2').value);
    const resultadoElement = document.getElementById('resultadoCalc');
    
    // Validamos que los inputs sean números válidos
    if (isNaN(num1) || isNaN(num2)) {
        resultadoElement.innerHTML = "Error: Por favor, ingresa números válidos";
        resultadoElement.classList.add('error');
        return;
    }
    
    // Llamamos a la función correspondiente
    const resultado = operaciones[operacion](num1, num2);
    
    // Mostramos el resultado
    resultadoElement.innerHTML = `
        <strong>Operación:</strong> ${operacion}<br>
        <strong>Números:</strong> ${num1} y ${num2}<br>
        <strong>Resultado:</strong> ${resultado}
    `;
    resultadoElement.classList.remove('error');
}
```

2. Prueba la calculadora ingresando dos números y haciendo clic en los diferentes botones de operación.

## Ejercicio 5: Desafíos Adicionales

Añade estos desafíos avanzados a tu archivo JavaScript:

```javascript
// ===== DESAFÍOS ADICIONALES =====
// (Añade botones y elementos de salida en el HTML para probarlos)

// 1. Memoización (optimización de funciones)
function crearCalculadoraFibonacci() {
    const cache = {};
    
    return function fibonacci(n) {
        // Si ya calculamos este valor, lo retornamos directamente
        if (n in cache) {
            return cache[n];
        }
        
        // Calculamos el valor para n
        let resultado;
        if (n <= 1) {
            resultado = n;
        } else {
            resultado = fibonacci(n - 1) + fibonacci(n - 2);
        }
        
        // Guardamos el resultado en caché para futuros usos
        cache[n] = resultado;
        return resultado;
    };
}

// 2. Currying (transformar función con múltiples argumentos en secuencia de funciones)
function curriedSum(a) {
    return function(b) {
        return function(c) {
            return a + b + c;
        };
    };
}

// 3. Composición de funciones
function componer(...funciones) {
    return function(valor) {
        return funciones.reduceRight((valorActual, funcion) => funcion(valorActual), valor);
    };
}

const duplicar = x => x * 2;
const sumarUno = x => x + 1;
const cuadrado = x => x * x;

// Componemos: cuadrado(sumarUno(duplicar(x)))
const operacionCompuesta = componer(cuadrado, sumarUno, duplicar);
```

## Entrega

Para completar esta práctica, debes entregar:

1. El archivo HTML `practica-funciones.html`.
2. El archivo JavaScript `funciones.js` con todas las funciones implementadas.
3. Un breve informe (en un archivo de texto o comentarios en el código) donde expliques:
   - Las diferencias entre los tipos de declaración de funciones.
   - El concepto de closure y sus aplicaciones.
   - Las ventajas de las funciones puras.
   - Al menos un caso práctico donde usarías recursión.

## Evaluación

Se evaluará:
- Implementación correcta de los diferentes tipos de funciones.
- Uso adecuado de parámetros y valores de retorno.
- Comprensión de conceptos avanzados (closures, recursión, etc.).
- Funcionamiento correcto de la calculadora.
- Claridad y estructura del código.
- Implementación y comprensión de los desafíos adicionales (opcional para calificación máxima). 