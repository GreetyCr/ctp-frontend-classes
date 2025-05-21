# Práctica 4: Colores y Tipografía en CSS

## Objetivos
- Comprender y aplicar diferentes sistemas de colores en CSS
- Dominar las propiedades tipográficas en CSS
- Crear diseños visualmente atractivos mediante el uso efectivo de colores y tipografía

## Ejercicio 1: Sistemas de Colores

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistemas de Colores en CSS</title>
    <link rel="stylesheet" href="colores.css">
</head>
<body>
    <h1>Sistemas de Colores en CSS</h1>
    
    <section class="seccion">
        <h2>1. Colores con Nombres</h2>
        <div class="contenedor colores-nombres">
            <div class="color-box red">Red</div>
            <div class="color-box blue">Blue</div>
            <div class="color-box green">Green</div>
            <div class="color-box yellow">Yellow</div>
            <div class="color-box purple">Purple</div>
            <div class="color-box orange">Orange</div>
            <div class="color-box black">Black</div>
            <div class="color-box white">White</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>2. Colores Hexadecimales</h2>
        <div class="contenedor colores-hex">
            <div class="color-box" style="background-color: #FF0000;">#FF0000</div>
            <div class="color-box" style="background-color: #00FF00;">#00FF00</div>
            <div class="color-box" style="background-color: #0000FF;">#0000FF</div>
            <div class="color-box" style="background-color: #FFFF00;">#FFFF00</div>
            <div class="color-box" style="background-color: #FF00FF;">#FF00FF</div>
            <div class="color-box" style="background-color: #00FFFF;">#00FFFF</div>
            <div class="color-box" style="background-color: #C0C0C0;">#C0C0C0</div>
            <div class="color-box" style="background-color: #808080;">#808080</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>3. Colores RGB</h2>
        <div class="contenedor colores-rgb">
            <div class="color-box" style="background-color: rgb(255, 0, 0);">rgb(255, 0, 0)</div>
            <div class="color-box" style="background-color: rgb(0, 255, 0);">rgb(0, 255, 0)</div>
            <div class="color-box" style="background-color: rgb(0, 0, 255);">rgb(0, 0, 255)</div>
            <div class="color-box" style="background-color: rgb(255, 255, 0);">rgb(255, 255, 0)</div>
            <div class="color-box" style="background-color: rgb(255, 0, 255);">rgb(255, 0, 255)</div>
            <div class="color-box" style="background-color: rgb(0, 255, 255);">rgb(0, 255, 255)</div>
            <div class="color-box" style="background-color: rgb(192, 192, 192);">rgb(192, 192, 192)</div>
            <div class="color-box" style="background-color: rgb(128, 128, 128);">rgb(128, 128, 128)</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>4. Colores RGBA (con transparencia)</h2>
        <div class="contenedor colores-rgba">
            <div class="bg-pattern">
                <div class="color-box" style="background-color: rgba(255, 0, 0, 1);">rgba(255, 0, 0, 1)</div>
                <div class="color-box" style="background-color: rgba(255, 0, 0, 0.8);">rgba(255, 0, 0, 0.8)</div>
                <div class="color-box" style="background-color: rgba(255, 0, 0, 0.6);">rgba(255, 0, 0, 0.6)</div>
                <div class="color-box" style="background-color: rgba(255, 0, 0, 0.4);">rgba(255, 0, 0, 0.4)</div>
                <div class="color-box" style="background-color: rgba(255, 0, 0, 0.2);">rgba(255, 0, 0, 0.2)</div>
            </div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>5. Colores HSL</h2>
        <div class="contenedor colores-hsl">
            <div class="color-box" style="background-color: hsl(0, 100%, 50%);">hsl(0, 100%, 50%)</div>
            <div class="color-box" style="background-color: hsl(60, 100%, 50%);">hsl(60, 100%, 50%)</div>
            <div class="color-box" style="background-color: hsl(120, 100%, 50%);">hsl(120, 100%, 50%)</div>
            <div class="color-box" style="background-color: hsl(180, 100%, 50%);">hsl(180, 100%, 50%)</div>
            <div class="color-box" style="background-color: hsl(240, 100%, 50%);">hsl(240, 100%, 50%)</div>
            <div class="color-box" style="background-color: hsl(300, 100%, 50%);">hsl(300, 100%, 50%)</div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>6. Colores HSLA (con transparencia)</h2>
        <div class="contenedor colores-hsla">
            <div class="bg-pattern">
                <div class="color-box" style="background-color: hsla(240, 100%, 50%, 1);">hsla(240, 100%, 50%, 1)</div>
                <div class="color-box" style="background-color: hsla(240, 100%, 50%, 0.8);">hsla(240, 100%, 50%, 0.8)</div>
                <div class="color-box" style="background-color: hsla(240, 100%, 50%, 0.6);">hsla(240, 100%, 50%, 0.6)</div>
                <div class="color-box" style="background-color: hsla(240, 100%, 50%, 0.4);">hsla(240, 100%, 50%, 0.4)</div>
                <div class="color-box" style="background-color: hsla(240, 100%, 50%, 0.2);">hsla(240, 100%, 50%, 0.2)</div>
            </div>
        </div>
    </section>
    
    <section class="seccion">
        <h2>7. Gradientes</h2>
        <div class="contenedor gradientes">
            <div class="gradient-box lineal">Gradiente Lineal</div>
            <div class="gradient-box radial">Gradiente Radial</div>
            <div class="gradient-box conic">Gradiente Cónico</div>
            <div class="gradient-box multi">Gradiente Multi-Color</div>
            <div class="gradient-box repetido">Gradiente Repetido</div>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "colores.css" y aplica los siguientes requisitos:

1. Estilos generales:
   - Define un estilo para el body (fuente, color, margen)
   - Estiliza los encabezados y las secciones

2. Para los contenedores de colores:
   - Crea un diseño flexible para mostrar los ejemplos de colores
   - Define un estilo base para los cuadros de colores

3. Para los colores con nombres:
   - Utiliza los nombres de colores para configurar el background-color
   - Ajusta el color del texto para asegurar la legibilidad

4. Para los degradados:
   - Crea diferentes tipos de gradientes (lineal, radial, cónico)
   - Crea un degradado con múltiples colores
   - Crea un degradado repetido

5. Para mostrar la transparencia:
   - Crea un patrón de fondo (bg-pattern) para mostrar el efecto de transparencia
   - Aplica diferentes niveles de transparencia usando rgba y hsla

## Ejercicio 2: Tipografía

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tipografía en CSS</title>
    <link rel="stylesheet" href="tipografia.css">
    <!-- Agregar enlaces a las fuentes de Google -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&display=swap" rel="stylesheet">
</head>
<body>
    <h1>Tipografía en CSS</h1>
    
    <section class="seccion">
        <h2>1. Familias de Fuentes</h2>
        <div class="contenedor familias-fuentes">
            <p class="serif">Serif: "Times New Roman", Times, serif</p>
            <p class="sans-serif">Sans-serif: Arial, Helvetica, sans-serif</p>
            <p class="monospace">Monospace: "Courier New", Courier, monospace</p>
            <p class="cursive">Cursive: cursive</p>
            <p class="fantasy">Fantasy: fantasy</p>
            <p class="roboto">Google Font: Roboto</p>
            <p class="playfair">Google Font: Playfair Display</p>
            <p class="montserrat">Google Font: Montserrat</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>2. Tamaño de Fuente</h2>
        <div class="contenedor tamanos-fuente">
            <p class="px-12">Tamaño en px: 12px</p>
            <p class="px-16">Tamaño en px: 16px</p>
            <p class="px-24">Tamaño en px: 24px</p>
            <p class="em-1">Tamaño en em: 1em</p>
            <p class="em-1-5">Tamaño en em: 1.5em</p>
            <p class="em-2">Tamaño en em: 2em</p>
            <p class="rem-1">Tamaño en rem: 1rem</p>
            <p class="rem-1-5">Tamaño en rem: 1.5rem</p>
            <p class="rem-2">Tamaño en rem: 2rem</p>
            <p class="porcentaje-100">Tamaño en porcentaje: 100%</p>
            <p class="porcentaje-150">Tamaño en porcentaje: 150%</p>
            <p class="porcentaje-200">Tamaño en porcentaje: 200%</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>3. Estilo y Peso de Fuente</h2>
        <div class="contenedor estilo-peso">
            <p class="normal">Estilo normal</p>
            <p class="italic">Estilo italic</p>
            <p class="oblique">Estilo oblique</p>
            <p class="weight-100">Peso: 100 (Thin)</p>
            <p class="weight-300">Peso: 300 (Light)</p>
            <p class="weight-400">Peso: 400 (Regular)</p>
            <p class="weight-700">Peso: 700 (Bold)</p>
            <p class="weight-900">Peso: 900 (Black)</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>4. Transformación de Texto</h2>
        <div class="contenedor transformacion-texto">
            <p class="uppercase">Este texto está en MAYÚSCULAS</p>
            <p class="lowercase">ESTE TEXTO ESTÁ EN MINÚSCULAS</p>
            <p class="capitalize">este texto tiene la primera letra de cada palabra en mayúscula</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>5. Decoración y Alineación de Texto</h2>
        <div class="contenedor decoracion-alineacion">
            <p class="underline">Texto con subrayado</p>
            <p class="overline">Texto con línea superior</p>
            <p class="line-through">Texto tachado</p>
            <p class="align-left">Este texto está alineado a la izquierda</p>
            <p class="align-center">Este texto está centrado</p>
            <p class="align-right">Este texto está alineado a la derecha</p>
            <p class="align-justify">Este texto está justificado. Debe contener suficiente texto para mostrar el efecto de justificación, haciendo que el texto se distribuya uniformemente entre los márgenes izquierdo y derecho.</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>6. Espaciado</h2>
        <div class="contenedor espaciado">
            <p class="letter-spacing-1">Espaciado entre letras: 1px</p>
            <p class="letter-spacing-3">Espaciado entre letras: 3px</p>
            <p class="letter-spacing-5">Espaciado entre letras: 5px</p>
            <p class="word-spacing-5">Espaciado entre palabras: 5px</p>
            <p class="word-spacing-10">Espaciado entre palabras: 10px</p>
            <p class="word-spacing-15">Espaciado entre palabras: 15px</p>
            <p class="line-height-1">Altura de línea: 1<br>Segunda línea<br>Tercera línea</p>
            <p class="line-height-1-5">Altura de línea: 1.5<br>Segunda línea<br>Tercera línea</p>
            <p class="line-height-2">Altura de línea: 2<br>Segunda línea<br>Tercera línea</p>
        </div>
    </section>
    
    <section class="seccion">
        <h2>7. Sombras de Texto</h2>
        <div class="contenedor sombras-texto">
            <p class="shadow-simple">Sombra Simple</p>
            <p class="shadow-blur">Sombra con Desenfoque</p>
            <p class="shadow-multiple">Múltiples Sombras</p>
            <p class="shadow-neon">Efecto Neón</p>
            <p class="shadow-3d">Efecto 3D</p>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "tipografia.css" y aplica:

1. Estilos generales para el documento

2. Para las familias de fuentes:
   - Configura diferentes tipos de fuentes (serif, sans-serif, monospace, etc.)
   - Implementa fuentes de Google (Roboto, Playfair Display, Montserrat)

3. Para los tamaños de fuente:
   - Configura diferentes tamaños usando diversas unidades (px, em, rem, %)
   - Compara y contrasta el comportamiento de estas unidades

4. Para el estilo y peso de fuente:
   - Aplica diferentes estilos (normal, italic, oblique)
   - Aplica diferentes pesos (thin, light, regular, bold, black)

5. Para la transformación de texto:
   - Aplica diferentes transformaciones (uppercase, lowercase, capitalize)

6. Para la decoración y alineación:
   - Aplica decoraciones de texto (underline, overline, line-through)
   - Configura diferentes alineaciones (left, center, right, justify)

7. Para el espaciado:
   - Configura diferentes valores de letter-spacing
   - Configura diferentes valores de word-spacing
   - Configura diferentes valores de line-height

8. Para las sombras de texto:
   - Crea una sombra simple
   - Crea una sombra con desenfoque
   - Crea efectos con múltiples sombras
   - Crea un efecto de texto neón
   - Crea un efecto de texto 3D

## Ejercicio 3: Diseño con Colores y Tipografía

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diseño con Colores y Tipografía</title>
    <link rel="stylesheet" href="diseno.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <header class="header">
        <div class="logo">Viajes Increíbles</div>
        <nav class="menu">
            <a href="#" class="active">Inicio</a>
            <a href="#">Destinos</a>
            <a href="#">Paquetes</a>
            <a href="#">Galería</a>
            <a href="#">Contacto</a>
        </nav>
    </header>
    
    <section class="hero">
        <div class="hero-content">
            <h1>Descubre el mundo con nosotros</h1>
            <p class="subtitle">Experiencias inolvidables a precios increíbles</p>
            <a href="#" class="cta-button">Ver Ofertas</a>
        </div>
    </section>
    
    <section class="features">
        <h2>Nuestros servicios</h2>
        
        <div class="feature-cards">
            <div class="card">
                <div class="card-icon">✈️</div>
                <h3>Vuelos Internacionales</h3>
                <p>Conexiones a más de 100 destinos en todo el mundo con las mejores aerolíneas.</p>
            </div>
            
            <div class="card">
                <div class="card-icon">🏨</div>
                <h3>Hoteles de Lujo</h3>
                <p>Hospedaje en los mejores hoteles con servicio de primera clase y comodidades exclusivas.</p>
            </div>
            
            <div class="card">
                <div class="card-icon">🚗</div>
                <h3>Transporte Incluido</h3>
                <p>Traslados desde el aeropuerto hasta el hotel y tours locales incluidos en todos los paquetes.</p>
            </div>
        </div>
    </section>
    
    <section class="destinations">
        <h2>Destinos populares</h2>
        
        <div class="destination-grid">
            <div class="destination">
                <div class="destination-image" style="background-image: url('https://via.placeholder.com/600x400')"></div>
                <div class="destination-info">
                    <h3>París, Francia</h3>
                    <p class="price">Desde $1,200</p>
                    <p class="description">La ciudad del amor y la luz, con su icónica Torre Eiffel y la mejor gastronomía.</p>
                    <a href="#" class="btn-secondary">Ver detalles</a>
                </div>
            </div>
            
            <div class="destination">
                <div class="destination-image" style="background-image: url('https://via.placeholder.com/600x400')"></div>
                <div class="destination-info">
                    <h3>Tokio, Japón</h3>
                    <p class="price">Desde $1,500</p>
                    <p class="description">Una mezcla fascinante de tradición y modernidad en la capital japonesa.</p>
                    <a href="#" class="btn-secondary">Ver detalles</a>
                </div>
            </div>
            
            <div class="destination">
                <div class="destination-image" style="background-image: url('https://via.placeholder.com/600x400')"></div>
                <div class="destination-info">
                    <h3>Nueva York, EE.UU.</h3>
                    <p class="price">Desde $1,300</p>
                    <p class="description">La Gran Manzana con sus rascacielos, Broadway y experiencias únicas.</p>
                    <a href="#" class="btn-secondary">Ver detalles</a>
                </div>
            </div>
        </div>
    </section>
    
    <section class="testimonials">
        <h2>Lo que dicen nuestros clientes</h2>
        
        <div class="testimonial-container">
            <div class="testimonial">
                <div class="quote">"Un servicio excepcional. El viaje superó todas nuestras expectativas y el equipo estuvo siempre atento a nuestras necesidades."</div>
                <div class="author">- María Rodríguez</div>
            </div>
            
            <div class="testimonial">
                <div class="quote">"Todo perfectamente organizado. No tuvimos que preocuparnos por nada y pudimos disfrutar al máximo de nuestras vacaciones."</div>
                <div class="author">- Juan Pérez</div>
            </div>
        </div>
    </section>
    
    <footer class="footer">
        <div class="footer-container">
            <div class="footer-column">
                <h4>Viajes Increíbles</h4>
                <p>Tu compañero de viaje desde 2010.</p>
            </div>
            
            <div class="footer-column">
                <h4>Enlaces rápidos</h4>
                <ul>
                    <li><a href="#">Sobre nosotros</a></li>
                    <li><a href="#">Destinos</a></li>
                    <li><a href="#">Paquetes especiales</a></li>
                    <li><a href="#">Blog de viajes</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h4>Contacto</h4>
                <p>Email: info@viajesincreibles.com</p>
                <p>Teléfono: (123) 456-7890</p>
            </div>
        </div>
        
        <div class="copyright">
            <p>© 2023 Viajes Increíbles. Todos los derechos reservados.</p>
        </div>
    </footer>
</body>
</html>
```

Crea un archivo CSS llamado "diseno.css" y aplica todo lo aprendido sobre colores y tipografía:

1. Define una paleta de colores:
   - Colores primarios, secundarios y neutros
   - Utiliza HSL para mayor control sobre los tonos
   - Opcional: utiliza variables CSS para definir tu paleta

2. Configura la tipografía:
   - Utiliza una fuente principal para el contenido (Poppins)
   - Utiliza una fuente secundaria para los títulos (Merriweather)
   - Define estilos base para todos los elementos tipográficos

3. Para la sección hero:
   - Aplica un degradado al fondo
   - Estiliza el texto con sombras y colores contrastantes
   - Crea un botón CTA atractivo con efectos hover

4. Para las tarjetas de características:
   - Utiliza sombras de caja
   - Aplica colores de fondo sutiles
   - Asegúrate de que la tipografía sea legible y atractiva

5. Para la sección de destinos:
   - Aplica efectos de superposición de color en las imágenes
   - Crea un contraste adecuado entre el texto y el fondo
   - Estiliza los precios y botones de manera distintiva

6. Para los testimonios:
   - Utiliza comillas y tipografía estilizada para las citas
   - Aplica un fondo o borde sutiles a las cajas de testimonios
   - Estiliza el nombre del autor de manera diferente al contenido del testimonio

7. Para el pie de página:
   - Utiliza colores de fondo contrastantes con el resto de la página
   - Asegúrate de que los enlaces sean claros y legibles
   - Aplica la tipografía y colores de manera coherente con el resto del diseño

## Entrega

Para completar esta práctica, debes entregar:

1. Los tres archivos HTML creados
2. Los tres archivos CSS correspondientes
3. Un breve documento explicando:
   - Tu elección de colores y tipografía para el ejercicio 3
   - Cómo has aplicado los principios aprendidos para crear un diseño coherente
   - Qué aspectos del diseño consideras más exitosos y por qué

## Recursos Adicionales

- [MDN Web Docs: Colores CSS](https://developer.mozilla.org/es/docs/Web/CSS/color)
- [MDN Web Docs: Tipografía Web](https://developer.mozilla.org/es/docs/Learn/CSS/Styling_text/Fundamentals)
- [Google Fonts](https://fonts.google.com/)
- [Adobe Color](https://color.adobe.com/es/create/color-wheel) - Para crear paletas de colores
- [Coolors](https://coolors.co/) - Generador de esquemas de color 