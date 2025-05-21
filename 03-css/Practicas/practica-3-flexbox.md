# Práctica 3: Flexbox en CSS

## Objetivos
- Comprender y aplicar los conceptos fundamentales de Flexbox
- Crear diseños flexibles y responsivos utilizando Flexbox
- Resolver problemas comunes de layout con Flexbox

## Ejercicio 1: Conceptos Básicos de Flexbox

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conceptos Básicos de Flexbox</title>
    <link rel="stylesheet" href="flexbox-basico.css">
</head>
<body>
    <h1>Práctica: Conceptos Básicos de Flexbox</h1>
    
    <section class="seccion">
        <h2>1. Flex Container y Flex Items</h2>
        <div class="contenedor contenedor-basico">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
        </div>
    </section>

    <section class="seccion">
        <h2>2. Flex Direction</h2>
        <h3>Row (predeterminado)</h3>
        <div class="contenedor direction-row">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
        </div>

        <h3>Column</h3>
        <div class="contenedor direction-column">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
        </div>

        <h3>Row Reverse</h3>
        <div class="contenedor direction-row-reverse">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
        </div>

        <h3>Column Reverse</h3>
        <div class="contenedor direction-column-reverse">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
        </div>
    </section>

    <section class="seccion">
        <h2>3. Flex Wrap</h2>
        <h3>Nowrap (predeterminado)</h3>
        <div class="contenedor wrap-nowrap">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
            <div class="item">7</div>
            <div class="item">8</div>
            <div class="item">9</div>
            <div class="item">10</div>
        </div>

        <h3>Wrap</h3>
        <div class="contenedor wrap-wrap">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
            <div class="item">7</div>
            <div class="item">8</div>
            <div class="item">9</div>
            <div class="item">10</div>
        </div>

        <h3>Wrap Reverse</h3>
        <div class="contenedor wrap-reverse">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
            <div class="item">7</div>
            <div class="item">8</div>
            <div class="item">9</div>
            <div class="item">10</div>
        </div>
    </section>

    <section class="seccion">
        <h2>4. Justify Content</h2>
        <h3>Flex-Start</h3>
        <div class="contenedor justify-start">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Flex-End</h3>
        <div class="contenedor justify-end">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Center</h3>
        <div class="contenedor justify-center">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Space-Between</h3>
        <div class="contenedor justify-between">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Space-Around</h3>
        <div class="contenedor justify-around">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Space-Evenly</h3>
        <div class="contenedor justify-evenly">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>
    </section>

    <section class="seccion">
        <h2>5. Align Items</h2>
        <h3>Stretch (predeterminado)</h3>
        <div class="contenedor align-stretch">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
        </div>

        <h3>Flex-Start</h3>
        <div class="contenedor align-start">
            <div class="item">1</div>
            <div class="item item-grande">2</div>
            <div class="item">3</div>
        </div>

        <h3>Flex-End</h3>
        <div class="contenedor align-end">
            <div class="item">1</div>
            <div class="item item-grande">2</div>
            <div class="item">3</div>
        </div>

        <h3>Center</h3>
        <div class="contenedor align-center">
            <div class="item">1</div>
            <div class="item item-grande">2</div>
            <div class="item">3</div>
        </div>

        <h3>Baseline</h3>
        <div class="contenedor align-baseline">
            <div class="item">1</div>
            <div class="item item-grande">2</div>
            <div class="item">3</div>
        </div>
    </section>

    <section class="seccion">
        <h2>6. Align Content</h2>
        <div class="contenedor-alto align-content-start">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
        </div>

        <div class="contenedor-alto align-content-end">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
        </div>

        <div class="contenedor-alto align-content-center">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
        </div>

        <div class="contenedor-alto align-content-between">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
        </div>

        <div class="contenedor-alto align-content-around">
            <div class="item">1</div>
            <div class="item">2</div>
            <div class="item">3</div>
            <div class="item">4</div>
            <div class="item">5</div>
            <div class="item">6</div>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "flexbox-basico.css" y aplica los siguientes requisitos:

1. Estilos generales:
   - Define un estilo para el body (fuente, color, margen)
   - Estiliza los encabezados y las secciones

2. Configura el contenedor Flex y sus elementos:
   - Define un estilo base para todos los contenedores con `display: flex`
   - Estiliza los elementos flexibles con colores, bordes y padding

3. Implementa los diferentes valores de flex-direction:
   - row (valor predeterminado)
   - column
   - row-reverse
   - column-reverse

4. Implementa los diferentes valores de flex-wrap:
   - nowrap
   - wrap
   - wrap-reverse

5. Implementa los diferentes valores de justify-content:
   - flex-start
   - flex-end
   - center
   - space-between
   - space-around
   - space-evenly

6. Implementa los diferentes valores de align-items:
   - stretch
   - flex-start
   - flex-end
   - center
   - baseline

7. Implementa los diferentes valores de align-content (en contenedores con wrap):
   - flex-start
   - flex-end
   - center
   - space-between
   - space-around

## Ejercicio 2: Propiedades de los Elementos Flexibles

Crea un nuevo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Propiedades de Elementos Flexibles</title>
    <link rel="stylesheet" href="flex-items.css">
</head>
<body>
    <h1>Propiedades de Elementos Flexibles (Flex Items)</h1>
    
    <section class="seccion">
        <h2>1. Flex Grow</h2>
        <div class="contenedor grow-ejemplo">
            <div class="item grow-0">grow: 0</div>
            <div class="item grow-1">grow: 1</div>
            <div class="item grow-2">grow: 2</div>
            <div class="item grow-3">grow: 3</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>2. Flex Shrink</h2>
        <div class="contenedor shrink-ejemplo">
            <div class="item shrink-0">shrink: 0</div>
            <div class="item shrink-1">shrink: 1</div>
            <div class="item shrink-2">shrink: 2</div>
            <div class="item shrink-3">shrink: 3</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>3. Flex Basis</h2>
        <div class="contenedor basis-ejemplo">
            <div class="item basis-auto">basis: auto</div>
            <div class="item basis-0">basis: 0</div>
            <div class="item basis-100">basis: 100px</div>
            <div class="item basis-200">basis: 200px</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>4. Propiedad Flex (shorthand)</h2>
        <div class="contenedor flex-ejemplo">
            <div class="item flex-1">flex: 1</div>
            <div class="item flex-1-100px">flex: 1 1 100px</div>
            <div class="item flex-0-0-auto">flex: 0 0 auto</div>
            <div class="item flex-2">flex: 2</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>5. Align Self</h2>
        <div class="contenedor align-self-ejemplo">
            <div class="item align-auto">auto</div>
            <div class="item align-start">flex-start</div>
            <div class="item align-end">flex-end</div>
            <div class="item align-center">center</div>
            <div class="item align-stretch">stretch</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>6. Order</h2>
        <div class="contenedor order-ejemplo">
            <div class="item order-3">order: 3</div>
            <div class="item order-1">order: 1</div>
            <div class="item order-4">order: 4</div>
            <div class="item order-2">order: 2</div>
            <div class="item order-0">order: 0 (default)</div>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "flex-items.css" y aplica:

1. Estilos generales similar al ejercicio anterior

2. Para los elementos con diferentes `flex-grow`:
   - El primero debe tener flex-grow: 0 (no crece)
   - Los demás deben tener valores de 1, 2 y 3 respectivamente
   - Muestra cómo se distribuye el espacio disponible

3. Para los elementos con diferentes `flex-shrink`:
   - Asegúrate de que el contenedor tenga un ancho limitado
   - Asigna valores de shrink de 0, 1, 2 y 3 a los elementos
   - Muestra cómo se encogen cuando no hay suficiente espacio

4. Para los elementos con diferentes `flex-basis`:
   - Muestra ejemplos con valores auto, 0, 100px y 200px
   - Explica cómo afecta al tamaño inicial

5. Para la propiedad `flex` (shorthand):
   - Muestra ejemplos de diferentes combinaciones de valores
   - Incluye casos comunes como flex: 1, flex: 0 0 auto, etc.

6. Para `align-self`:
   - Configura un contenedor con align-items predeterminado
   - Modifica cada elemento para usar un valor diferente de align-self

7. Para `order`:
   - Muestra cómo los elementos se reorganizan según su valor de order
   - Incluye un elemento con el valor predeterminado (0)

## Ejercicio 3: Layouts Prácticos con Flexbox

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layouts con Flexbox</title>
    <link rel="stylesheet" href="flexbox-layouts.css">
</head>
<body>
    <h1>Layouts Prácticos con Flexbox</h1>
    
    <section class="seccion">
        <h2>1. Barra de Navegación Responsive</h2>
        <header class="navbar">
            <div class="logo">Logo</div>
            <nav class="menu">
                <a href="#">Inicio</a>
                <a href="#">Servicios</a>
                <a href="#">Productos</a>
                <a href="#">Nosotros</a>
                <a href="#">Contacto</a>
            </nav>
        </header>
    </section>
    
    <section class="seccion">
        <h2>2. Layout de Tres Columnas</h2>
        <div class="tres-columnas">
            <aside class="sidebar izquierda">
                <h3>Menú Lateral</h3>
                <ul>
                    <li><a href="#">Enlace 1</a></li>
                    <li><a href="#">Enlace 2</a></li>
                    <li><a href="#">Enlace 3</a></li>
                    <li><a href="#">Enlace 4</a></li>
                </ul>
            </aside>
            
            <main class="contenido-principal">
                <h3>Contenido Principal</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla facilisi. Donec euismod, nisl eget ultricies ultricies, nisl nisl ultricies nisl, nec ultricies nisl nisl nec nisl.</p>
                <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante.</p>
            </main>
            
            <aside class="sidebar derecha">
                <h3>Panel Lateral</h3>
                <div class="widget">
                    <h4>Widget 1</h4>
                    <p>Contenido del widget</p>
                </div>
                <div class="widget">
                    <h4>Widget 2</h4>
                    <p>Contenido del widget</p>
                </div>
            </aside>
        </div>
    </section>
    
    <section class="seccion">
        <h2>3. Galería de Imágenes</h2>
        <div class="galeria">
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 1">
                <div class="caption">Imagen 1</div>
            </div>
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 2">
                <div class="caption">Imagen 2</div>
            </div>
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 3">
                <div class="caption">Imagen 3</div>
            </div>
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 4">
                <div class="caption">Imagen 4</div>
            </div>
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 5">
                <div class="caption">Imagen 5</div>
            </div>
            <div class="imagen-item">
                <img src="https://via.placeholder.com/300x200" alt="Imagen 6">
                <div class="caption">Imagen 6</div>
            </div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>4. Tarjetas con Altura Uniforme</h2>
        <div class="tarjetas">
            <div class="tarjeta">
                <h3>Tarjeta 1</h3>
                <p>Este es un contenido corto.</p>
                <button>Más información</button>
            </div>
            <div class="tarjeta">
                <h3>Tarjeta 2</h3>
                <p>Este es un contenido más largo que ocupa más espacio y posiblemente múltiples líneas para mostrar cómo se comporta el flexbox con alturas diferentes.</p>
                <button>Más información</button>
            </div>
            <div class="tarjeta">
                <h3>Tarjeta 3</h3>
                <p>Otro contenido de longitud media que usamos para mostrar el comportamiento de flexbox.</p>
                <button>Más información</button>
            </div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>5. Layout de Página Completa</h2>
        <div class="pagina-completa">
            <header class="encabezado">
                <h3>Encabezado de Página</h3>
            </header>
            
            <div class="contenido-pagina">
                <nav class="nav-lateral">
                    <h4>Navegación</h4>
                    <ul>
                        <li><a href="#">Enlace 1</a></li>
                        <li><a href="#">Enlace 2</a></li>
                        <li><a href="#">Enlace 3</a></li>
                    </ul>
                </nav>
                
                <main class="contenido">
                    <h4>Contenido Principal</h4>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla facilisi. Donec euismod, nisl eget ultricies ultricies, nisl nisl ultricies nisl, nec ultricies nisl nisl nec nisl.</p>
                </main>
                
                <aside class="barra-lateral">
                    <h4>Barra Lateral</h4>
                    <p>Información adicional.</p>
                </aside>
            </div>
            
            <footer class="pie-pagina">
                <h3>Pie de Página</h3>
            </footer>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "flexbox-layouts.css" y aplica:

1. Para la barra de navegación:
   - Usa flexbox para crear una barra de navegación horizontal
   - Añade un media query para mostrarla verticalmente en dispositivos móviles
   - Aplica estilos adecuados para los enlaces

2. Para el layout de tres columnas:
   - Crea un contenedor flex con tres secciones
   - Asigna diferentes valores de flex a cada columna
   - Haz que sea responsive (apilando las columnas en pantallas pequeñas)

3. Para la galería de imágenes:
   - Crea una galería con flex que muestre las imágenes en filas
   - Asegúrate de que se ajusten automáticamente dependiendo del ancho
   - Aplica estilos para los elementos de la galería y las leyendas

4. Para las tarjetas con altura uniforme:
   - Crea tarjetas que mantengan la misma altura independientemente de su contenido
   - Asegúrate de que los botones estén alineados en la parte inferior
   - Aplica márgenes y estilos adecuados

5. Para el layout de página completa:
   - Crea un layout flexible con encabezado, contenido principal, barras laterales y pie de página
   - Utiliza flex-direction para organizar los elementos vertical y horizontalmente
   - Asegúrate de que sea responsive

## Entrega

Para completar esta práctica, debes entregar:

1. Los tres archivos HTML creados
2. Los tres archivos CSS correspondientes
3. Un breve documento explicando:
   - Cómo has aplicado Flexbox para resolver cada ejercicio
   - Desafíos que encontraste y cómo los resolviste
   - Ventajas que observaste al usar Flexbox para estos layouts

## Recursos Adicionales

- [MDN Web Docs: Flexbox](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout/Flexbox)
- [CSS-Tricks: Guía Completa de Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/#es) - Juego para aprender Flexbox 