# Práctica 1: Variables y Operadores en JavaScript

## Objetivos
- Comprender los diferentes tipos de variables en JavaScript
- Practicar el uso de operadores aritméticos, de asignación, comparación y lógicos
- Aplicar conocimientos de conversión de tipos y coerción

## Ejercicio 1: Declaración y asignación de variables

1. Crea un archivo HTML con el nombre `practica-variables.html` y añade la estructura básica.
2. Agrega un archivo JavaScript con el nombre `script.js` y enlázalo al archivo HTML.
3. En tu archivo JavaScript, declara variables utilizando `var`, `let` y `const` como se muestra a continuación:

```javascript
// Declara variables con var
var nombre = "María";
var edad = 25;
var esDeveloper = true;

// Declara variables con let
let ciudad = "Madrid";
let temperatura = 22.5;
let tieneMascota = false;

// Declara constantes
const PI = 3.1416;
const DIAS_SEMANA = 7;
const COLORES_PRIMARIOS = ["rojo", "azul", "amarillo"];
```

4. Muestra el valor de cada variable en la consola usando `console.log()`.
5. Trata de reasignar un valor a una constante y observa el error que se produce.
6. Explora el ámbito (scope) de las variables creando bloques de código con `{}` y declarando variables dentro y fuera de estos bloques.

## Ejercicio 2: Operadores aritméticos

1. Crea un nuevo archivo `operadores-aritmeticos.js`.
2. Declara las siguientes variables:

```javascript
let a = 10;
let b = 3;
```

3. Realiza y muestra en consola las siguientes operaciones:
   - Suma de `a` y `b`
   - Resta de `a` y `b`
   - Multiplicación de `a` y `b`
   - División de `a` entre `b`
   - El resto de dividir `a` entre `b`
   - `a` elevado a la potencia de `b`
   - Incrementa en 1 el valor de `a` y muéstralo
   - Decrementa en 1 el valor de `b` y muéstralo

4. Crea una variable `resultado` y asígnale el valor de una expresión compleja que utilice al menos 3 operadores aritméticos diferentes.

## Ejercicio 3: Operadores de asignación

1. Crea un nuevo archivo `operadores-asignacion.js`.
2. Declara una variable `x` con el valor inicial de 10.
3. Utiliza los siguientes operadores de asignación y muestra el resultado después de cada operación:
   - `+=` para sumar 5 a `x`
   - `-=` para restar 3 a `x`
   - `*=` para multiplicar `x` por 2
   - `/=` para dividir `x` entre 4
   - `%=` para calcular el resto de dividir `x` entre 3

## Ejercicio 4: Operadores de comparación

1. Crea un nuevo archivo `operadores-comparacion.js`.
2. Declara las siguientes variables:

```javascript
let num1 = 5;
let num2 = "5";
let num3 = 8;
```

3. Realiza las siguientes comparaciones y muestra los resultados en la consola:
   - `num1 == num2` (igualdad simple)
   - `num1 === num2` (igualdad estricta)
   - `num1 != num2` (desigualdad simple)
   - `num1 !== num2` (desigualdad estricta)
   - `num1 < num3` (menor que)
   - `num1 > num3` (mayor que)
   - `num1 <= num2` (menor o igual que)
   - `num1 >= num3` (mayor o igual que)

4. Analiza y explica los resultados obtenidos, especialmente las diferencias entre los operadores `==` y `===`.

## Ejercicio 5: Operadores lógicos

1. Crea un nuevo archivo `operadores-logicos.js`.
2. Declara las siguientes variables:

```javascript
let esEstudiante = true;
let tieneBeca = false;
let edad = 20;
let promedio = 8.5;
```

3. Realiza las siguientes operaciones lógicas y muestra los resultados:
   - `esEstudiante && tieneBeca` (AND lógico)
   - `esEstudiante || tieneBeca` (OR lógico)
   - `!esEstudiante` (NOT lógico)
   - `(edad >= 18) && (promedio >= 8)` (combinación de operadores)
   - `(edad < 18) || (promedio > 9)` (combinación de operadores)

4. Explora el concepto de evaluación de cortocircuito con los operadores `&&` y `||`.

## Ejercicio 6: Conversión de tipos y operaciones con diferentes tipos

1. Crea un nuevo archivo `conversion-tipos.js`.
2. Declara las siguientes variables:

```javascript
let numero = 42;
let texto = "7";
let booleano = true;
```

3. Realiza las siguientes operaciones y analiza los resultados:
   - `numero + texto`
   - `numero - texto`
   - `numero * texto`
   - `numero / texto`
   - `numero + booleano`
   - `numero + Number(texto)`
   - `texto + booleano`
   - `String(numero) + texto`
   - `booleano + Number(texto)`

4. Utiliza explícitamente los métodos `Number()`, `String()` y `Boolean()` para convertir valores entre diferentes tipos.

## Ejercicio 7: Calculadora simple

1. Crea un archivo HTML llamado `calculadora.html` con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simple</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        .calculadora {
            border: 1px solid #ccc;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        input, select, button {
            padding: 8px;
            margin: 5px 0;
        }
        .resultado {
            margin-top: 15px;
            padding: 10px;
            background-color: #f4f4f4;
            border-left: 3px solid #333;
        }
    </style>
</head>
<body>
    <div class="calculadora">
        <h2>Calculadora Simple</h2>
        <div>
            <input type="number" id="num1" placeholder="Primer número">
            <select id="operacion">
                <option value="suma">+</option>
                <option value="resta">-</option>
                <option value="multiplicacion">×</option>
                <option value="division">÷</option>
            </select>
            <input type="number" id="num2" placeholder="Segundo número">
            <button onclick="calcular()">Calcular</button>
        </div>
        <div class="resultado" id="resultado">
            El resultado aparecerá aquí
        </div>
    </div>

    <script>
        function calcular() {
            // Implementa esta función
        }
    </script>
</body>
</html>
```

2. Implementa la función `calcular()` de modo que:
   - Obtenga los valores numéricos de los campos de entrada
   - Determine qué operación se seleccionó en el menú desplegable
   - Realice la operación matemática correspondiente
   - Muestre el resultado en el elemento con ID "resultado"
   - Maneje posibles errores (como división por cero)

## Entrega
Para completar esta práctica, debes entregar:

1. Los archivos `.js` correspondientes a cada ejercicio.
2. El archivo HTML de la calculadora con la función implementada.
3. Un pequeño informe (en un archivo README.md o en comentarios) que explique los conceptos más importantes que has aprendido y cualquier dificultad que hayas encontrado.

## Evaluación
Se evaluará:
- Correcto uso de variables y constantes
- Comprensión de los diferentes operadores
- Manejo de la conversión de tipos
- Implementación de la calculadora simple
- Calidad y legibilidad del código
- Explicaciones y análisis de los resultados 