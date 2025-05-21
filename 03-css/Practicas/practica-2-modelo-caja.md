# Práctica 2: Modelo de Caja en CSS

## Objetivos
- Comprender en profundidad el modelo de caja de CSS
- Dominar las propiedades de dimensiones, márgenes, relleno y bordes
- Experimentar con diferentes estrategias de dimensionamiento de cajas

## Ejercicio 1: Comparación de Modelos de Caja

Crea un archivo HTML con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modelo de Caja en CSS</title>
    <link rel="stylesheet" href="modelo-caja.css">
</head>
<body>
    <h1>Práctica: Modelo de Caja en CSS</h1>
    
    <section class="contenedor">
        <h2>Comparación de Modelos de Caja</h2>
        
        <div class="caja content-box">
            <h3>Content-Box (Estándar)</h3>
            <p>En este modelo, el ancho y alto especificados se aplican solo al contenido. 
            El padding y el borde se añaden al ancho total.</p>
        </div>
        
        <div class="caja border-box">
            <h3>Border-Box (Alternativo)</h3>
            <p>En este modelo, el ancho y alto especificados incluyen el contenido, 
            el padding y el borde, pero no el margen.</p>
        </div>
    </section>
    
    <section class="dimensiones">
        <h2>Dimensionamiento de Cajas</h2>
        
        <div class="caja-dim ancho-fijo">
            <h3>Ancho Fijo</h3>
            <p>Esta caja tiene un ancho fijo en píxeles.</p>
        </div>
        
        <div class="caja-dim ancho-porcentaje">
            <h3>Ancho Porcentual</h3>
            <p>Esta caja tiene un ancho en porcentaje relativo a su contenedor.</p>
        </div>
        
        <div class="caja-dim min-max">
            <h3>Min/Max Width</h3>
            <p>Esta caja tiene valores mínimos y máximos para su ancho.</p>
        </div>
    </section>
    
    <section class="margenes-relleno">
        <h2>Márgenes y Relleno</h2>
        
        <div class="caja-margen ejemplo-margen">
            <h3>Márgenes</h3>
            <p>Esta caja tiene diferentes valores de margen en cada lado.</p>
        </div>
        
        <div class="caja-margen ejemplo-relleno">
            <h3>Relleno (Padding)</h3>
            <p>Esta caja tiene diferentes valores de relleno en cada lado.</p>
        </div>
        
        <div class="caja-margen ejemplo-colapso1">
            <h3>Colapso de Márgenes 1</h3>
            <p>Este es un ejemplo de colapso de márgenes verticales.</p>
        </div>
        
        <div class="caja-margen ejemplo-colapso2">
            <h3>Colapso de Márgenes 2</h3>
            <p>Observa cómo los márgenes verticales colapsan entre estas cajas.</p>
        </div>
    </section>
    
    <section class="bordes">
        <h2>Bordes y Contornos</h2>
        
        <div class="caja-borde borde-solido">
            <h3>Borde Sólido</h3>
            <p>Ejemplo de borde sólido.</p>
        </div>
        
        <div class="caja-borde borde-punteado">
            <h3>Borde Punteado</h3>
            <p>Ejemplo de borde punteado.</p>
        </div>
        
        <div class="caja-borde borde-discontinuo">
            <h3>Borde Discontinuo</h3>
            <p>Ejemplo de borde discontinuo.</p>
        </div>
        
        <div class="caja-borde borde-doble">
            <h3>Borde Doble</h3>
            <p>Ejemplo de borde doble.</p>
        </div>
        
        <div class="caja-borde borde-redondeado">
            <h3>Bordes Redondeados</h3>
            <p>Ejemplo de bordes redondeados con diferentes radios.</p>
        </div>
        
        <div class="caja-borde con-outline">
            <h3>Outline (Contorno)</h3>
            <p>Ejemplo de outline alrededor de un borde.</p>
        </div>
    </section>
    
    <section class="sombras">
        <h2>Sombras de Caja</h2>
        
        <div class="caja-sombra sombra-exterior">
            <h3>Sombra Exterior</h3>
            <p>Ejemplo de una sombra exterior básica.</p>
        </div>
        
        <div class="caja-sombra sombra-interior">
            <h3>Sombra Interior</h3>
            <p>Ejemplo de una sombra interior (inset).</p>
        </div>
        
        <div class="caja-sombra sombras-multiples">
            <h3>Sombras Múltiples</h3>
            <p>Ejemplo de múltiples sombras combinadas.</p>
        </div>
    </section>
    
    <section class="overflow">
        <h2>Desbordamiento (Overflow)</h2>
        
        <div class="caja-overflow overflow-visible">
            <h3>Overflow Visible</h3>
            <p>Este es el comportamiento predeterminado. El contenido se mostrará fuera de la caja si es necesario.</p>
            <div class="contenido-largo">
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
            </div>
        </div>
        
        <div class="caja-overflow overflow-hidden">
            <h3>Overflow Hidden</h3>
            <p>El contenido que desborda se ocultará.</p>
            <div class="contenido-largo">
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
            </div>
        </div>
        
        <div class="caja-overflow overflow-scroll">
            <h3>Overflow Scroll</h3>
            <p>Aparecerán barras de desplazamiento, incluso si no son necesarias.</p>
            <div class="contenido-largo">
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
            </div>
        </div>
        
        <div class="caja-overflow overflow-auto">
            <h3>Overflow Auto</h3>
            <p>Las barras de desplazamiento aparecerán solo si son necesarias.</p>
            <div class="contenido-largo">
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
                Este es un contenido muy largo que debería desbordar la caja.
            </div>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "modelo-caja.css" y aplica los siguientes requisitos:

1. Estilos generales para el body y los encabezados
2. Para la sección "Comparación de Modelos de Caja":
   - Aplica `box-sizing: content-box` a la primera caja
   - Aplica `box-sizing: border-box` a la segunda caja
   - Asigna el mismo ancho, padding y borde a ambas cajas para mostrar la diferencia

3. Para la sección "Dimensionamiento de Cajas":
   - Crea una caja con ancho fijo en píxeles
   - Crea una caja con ancho en porcentaje (%)
   - Crea una caja con min-width y max-width

4. Para la sección "Márgenes y Relleno":
   - Aplica distintos valores de margen a cada lado de una caja
   - Aplica distintos valores de padding a cada lado de una caja
   - Crea dos cajas con márgenes verticales para demostrar el colapso de márgenes

5. Para la sección "Bordes y Contornos":
   - Crea ejemplos de diferentes estilos de borde (solid, dotted, dashed, double)
   - Crea una caja con bordes redondeados (diferentes radios en cada esquina)
   - Crea una caja con borde y outline

6. Para la sección "Sombras de Caja":
   - Aplica una sombra exterior básica
   - Aplica una sombra interior (inset)
   - Combina múltiples sombras en una caja

7. Para la sección "Desbordamiento (Overflow)":
   - Configura diferentes valores de overflow (visible, hidden, scroll, auto)
   - Asegúrate de que el contenido sobrepase las dimensiones para ver los efectos

## Ejercicio 2: Medidas Relativas

Crea un nuevo HTML con esta estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas Relativas</title>
    <link rel="stylesheet" href="medidas-relativas.css">
</head>
<body>
    <h1>Ejercicio de Medidas Relativas</h1>
    
    <section class="contenedor-em">
        <h2>Unidades EM</h2>
        <div class="em-externo">
            <p>Este es un texto en un contenedor externo.</p>
            <div class="em-interno">
                <p>Este es un texto en un contenedor interno.</p>
                <div class="em-interno-2">
                    <p>Este es un texto aún más anidado.</p>
                </div>
            </div>
        </div>
    </section>
    
    <section class="contenedor-rem">
        <h2>Unidades REM</h2>
        <div class="rem-externo">
            <p>Este es un texto en un contenedor externo.</p>
            <div class="rem-interno">
                <p>Este es un texto en un contenedor interno.</p>
                <div class="rem-interno-2">
                    <p>Este es un texto aún más anidado.</p>
                </div>
            </div>
        </div>
    </section>
    
    <section class="contenedor-porcentaje">
        <h2>Porcentajes</h2>
        <div class="porcentaje-padre">
            <div class="porcentaje-hijo-50">
                <p>Este elemento hijo ocupa el 50% del ancho del padre</p>
            </div>
            <div class="porcentaje-hijo-30">
                <p>Este elemento hijo ocupa el 30% del ancho del padre</p>
            </div>
        </div>
    </section>
    
    <section class="contenedor-viewport">
        <h2>Unidades de Viewport</h2>
        <div class="viewport-width">
            <p>Este elemento usa vw para su ancho</p>
        </div>
        <div class="viewport-height">
            <p>Este elemento usa vh para su altura</p>
        </div>
        <div class="viewport-min">
            <p>Este elemento usa vmin para su tamaño</p>
        </div>
        <div class="viewport-max">
            <p>Este elemento usa vmax para su tamaño</p>
        </div>
    </section>
</body>
</html>
```

Crea un archivo CSS llamado "medidas-relativas.css" y aplica:

1. Unidades EM:
   - Configura un tamaño de fuente base en el contenedor padre
   - Usa EM para tamaños de fuente en elementos anidados
   - Demuestra cómo los EM se acumulan en elementos anidados

2. Unidades REM:
   - Configura un tamaño de fuente base en el elemento html
   - Usa REM para tamaños de fuente en elementos anidados
   - Compara con los resultados de EM para mostrar que no se acumulan

3. Porcentajes:
   - Crea un contenedor padre con ancho definido
   - Crea elementos hijos con anchos porcentuales (50%, 30%, etc.)
   - Muestra cómo los porcentajes respetan el contenedor padre

4. Unidades de Viewport:
   - Usa vw (viewport width) para el ancho de un elemento
   - Usa vh (viewport height) para la altura de un elemento
   - Usa vmin y vmax para otros elementos
   - Cambia el tamaño de la ventana del navegador para ver cómo estas unidades responden

## Ejercicio 3: Desafío de Diseño de Tarjetas

Crea un diseño de tarjetas que combine todo lo aprendido sobre el modelo de caja:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diseño de Tarjetas</title>
    <link rel="stylesheet" href="tarjetas.css">
</head>
<body>
    <h1>Galería de Tarjetas</h1>
    
    <div class="galeria">
        <div class="tarjeta">
            <div class="tarjeta-imagen">
                <img src="https://via.placeholder.com/300x200" alt="Imagen de placeholder">
            </div>
            <div class="tarjeta-contenido">
                <h3>Tarjeta 1</h3>
                <p>Descripción de la tarjeta 1. Este es un texto de ejemplo para la primera tarjeta.</p>
                <a href="#" class="boton">Más información</a>
            </div>
        </div>
        
        <div class="tarjeta">
            <div class="tarjeta-imagen">
                <img src="https://via.placeholder.com/300x200" alt="Imagen de placeholder">
            </div>
            <div class="tarjeta-contenido">
                <h3>Tarjeta 2</h3>
                <p>Descripción de la tarjeta 2. Este texto puede ser más largo que el de la primera tarjeta para probar el comportamiento.</p>
                <a href="#" class="boton">Más información</a>
            </div>
        </div>
        
        <div class="tarjeta">
            <div class="tarjeta-imagen">
                <img src="https://via.placeholder.com/300x200" alt="Imagen de placeholder">
            </div>
            <div class="tarjeta-contenido">
                <h3>Tarjeta 3</h3>
                <p>Descripción de la tarjeta 3. Este es un ejemplo de texto corto.</p>
                <a href="#" class="boton">Más información</a>
            </div>
        </div>
    </div>
</body>
</html>
```

Crea un archivo CSS llamado "tarjetas.css" que aplique:

1. Un diseño de tarjetas atractivo con:
   - Box-sizing: border-box para todas las tarjetas
   - Ancho fijo o porcentual para las tarjetas
   - Bordes redondeados y sombras
   - Márgenes y padding adecuados
   - Control de overflow para el contenido y las imágenes
   - Efectos de hover con transiciones (opcional)

2. Asegúrate de que las tarjetas:
   - Mantengan la misma altura aunque tengan diferentes cantidades de contenido
   - Tengan un diseño coherente y limpio
   - Utilicen el modelo de caja de manera eficiente

## Entrega

Para completar esta práctica, debes entregar:

1. Los tres archivos HTML creados
2. Los tres archivos CSS correspondientes
3. Un breve documento explicando:
   - Las diferencias que has observado entre los modelos content-box y border-box
   - Cómo funcionan las diferentes unidades relativas y cuándo usarías cada una
   - Los desafíos que enfrentaste en el diseño de tarjetas y cómo los resolviste

## Recursos Adicionales

- [MDN Web Docs: Modelo de Caja](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/El_modelo_de_caja)
- [CSS-Tricks: Box Sizing](https://css-tricks.com/box-sizing/)
- [Smashing Magazine: Understanding CSS Units](https://www.smashingmagazine.com/2016/05/fluid-typography/) 