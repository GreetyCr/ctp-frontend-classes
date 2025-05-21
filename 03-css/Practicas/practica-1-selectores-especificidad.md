# Práctica 1: Selectores y Especificidad en CSS

## Objetivos
- Comprender y aplicar diferentes tipos de selectores CSS
- Entender el concepto de especificidad y su importancia
- Practicar la resolución de conflictos de estilos

## Ejercicio 1: Selectores Básicos

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Selectores CSS</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <header>
        <h1>Práctica de Selectores CSS</h1>
        <nav>
            <ul>
                <li><a href="#seccion1">Sección 1</a></li>
                <li><a href="#seccion2">Sección 2</a></li>
                <li><a href="#seccion3">Sección 3</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="seccion1" class="seccion">
            <h2>Sección 1</h2>
            <p>Este es un párrafo de ejemplo. <span class="destacado">Este texto está destacado</span>.</p>
            <p class="especial">Este es un párrafo con clase especial.</p>
        </section>

        <section id="seccion2" class="seccion">
            <h2>Sección 2</h2>
            <p>Otro párrafo de ejemplo.</p>
            <div class="caja">
                <p>Texto dentro de una caja.</p>
            </div>
        </section>

        <section id="seccion3" class="seccion">
            <h2>Sección 3</h2>
            <form>
                <div class="campo">
                    <label for="nombre">Nombre:</label>
                    <input type="text" id="nombre" name="nombre">
                </div>
                <div class="campo">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email">
                </div>
                <button type="submit">Enviar</button>
            </form>
        </section>
    </main>

    <footer>
        <p>Pie de página</p>
    </footer>
</body>
</html>
```

Crea un archivo CSS llamado "estilos.css" y aplica los siguientes requisitos:

1. Utiliza selectores de elemento para:
   - Dar un color de fondo (#f5f5f5) a todo el body
   - Cambiar el color del texto de todos los párrafos a #333
   - Centrar el texto de los encabezados h1 y h2

2. Utiliza selectores de clase para:
   - Dar un borde y padding a los elementos con clase "seccion"
   - Poner en negrita y cambiar de color el texto con clase "destacado"
   - Estilizar los elementos con clase "caja" con un fondo de color y sombra

3. Utiliza selectores de ID para:
   - Dar un color de fondo específico a cada sección (#seccion1, #seccion2, #seccion3)

4. Utiliza selectores descendientes para:
   - Estilizar los elementos li dentro del nav
   - Cambiar el estilo de los párrafos dentro de .caja

5. Utiliza pseudo-clases para:
   - Cambiar el color de los enlaces cuando se pasa el cursor (hover)
   - Estilizar los campos de formulario cuando están en foco (focus)

## Ejercicio 2: Especificidad y Conflictos

Crea un nuevo documento HTML:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Especificidad CSS</title>
    <link rel="stylesheet" href="especificidad.css">
</head>
<body>
    <h1>Ejercicio de Especificidad</h1>
    
    <div class="contenedor" id="principal">
        <p class="texto importante">Este es un párrafo con múltiples clases.</p>
        <p class="texto">Este es un párrafo con una clase.</p>
        <p>Este es un párrafo sin clase.</p>
    </div>
    
    <div class="contenedor secundario">
        <p class="texto">Este es otro párrafo con clase.</p>
        <p>Este es otro párrafo sin clase.</p>
    </div>
</body>
</html>
```

Crea un archivo CSS llamado "especificidad.css" y resuelve los siguientes desafíos:

1. Crea reglas CSS que demuestren cada uno de estos escenarios:
   - Una regla con ID gana sobre una regla con clase
   - Múltiples clases pueden tener mayor especificidad que una sola clase
   - Un selector más específico gana sobre uno menos específico
   - !important puede anular las reglas normales de especificidad

2. Experimenta con estas reglas:
   ```css
   p { color: blue; }
   .texto { color: red; }
   #principal .texto { color: green; }
   .contenedor .texto.importante { color: purple; }
   p.texto { color: orange !important; }
   ```

   Explica qué color tendrá cada párrafo y por qué.

## Ejercicio 3: Selectores Avanzados

Crea un nuevo HTML con esta estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selectores Avanzados</title>
    <link rel="stylesheet" href="avanzados.css">
</head>
<body>
    <h1>Selectores Avanzados en CSS</h1>
    
    <div class="contenedor">
        <p>Primer párrafo</p>
        <p>Segundo párrafo</p>
        <p>Tercer párrafo</p>
        <p>Cuarto párrafo</p>
        <p>Quinto párrafo</p>
    </div>
    
    <ul class="lista">
        <li>Elemento 1</li>
        <li>Elemento 2</li>
        <li>Elemento 3</li>
        <li>Elemento 4</li>
        <li>Elemento 5</li>
    </ul>
    
    <form class="formulario">
        <input type="text" placeholder="Nombre">
        <input type="email" placeholder="Email" required>
        <input type="tel" placeholder="Teléfono">
        <input type="checkbox" id="terminos"> <label for="terminos">Acepto los términos</label>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```

Crea un archivo CSS llamado "avanzados.css" y utiliza los siguientes selectores avanzados:

1. Selectores de atributo:
   - Estiliza los inputs por tipo ([type="text"], [type="email"], etc.)
   - Estiliza los elementos required

2. Pseudo-elementos:
   - Añade contenido después (::after) o antes (::before) de ciertos elementos
   - Estiliza la primera línea (::first-line) de un párrafo

3. Pseudo-clases estructurales:
   - Estiliza el primer y último párrafo (:first-child, :last-child)
   - Estiliza los elementos pares e impares de la lista (:nth-child(even), :nth-child(odd))
   - Estiliza un elemento específico de la lista (:nth-child(3))

4. Combinadores:
   - Utiliza el combinador de hermanos adyacentes (p + p)
   - Utiliza el combinador de hermanos generales (h1 ~ p)
   - Utiliza el combinador hijo directo (div > p)

## Entrega

Para completar esta práctica, debes entregar:

1. Los tres archivos HTML creados
2. Los tres archivos CSS correspondientes
3. Un breve documento explicando:
   - Cómo has aplicado cada tipo de selector
   - Ejemplos de especificidad y cómo has resuelto los conflictos
   - Qué has aprendido sobre los selectores avanzados

## Recursos Adicionales

- [MDN Web Docs: Selectores CSS](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Selectores_CSS)
- [CSS-Tricks: Especificidad](https://css-tricks.com/specifics-on-css-specificity/)
- [Juego para practicar selectores: CSS Diner](https://flukeout.github.io/) 