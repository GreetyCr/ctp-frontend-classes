# Práctica 6: Variables CSS y Metodologías de Organización

## Objetivos

- Aplicar variables CSS (custom properties) en un proyecto real
- Implementar una metodología de organización CSS (BEM, SMACSS o ITCSS)
- Crear un sistema de diseño coherente mediante variables
- Mejorar la mantenibilidad del código CSS
- Practicar el cambio dinámico de variables CSS con JavaScript

## Ejercicio 1: Sistema de Diseño con Variables CSS

Crea un sistema de diseño básico utilizando variables CSS que incluya:

1. **Sistema de Colores**
   - Colores principales (primario, secundario, acento)
   - Variaciones claras y oscuras de los colores principales
   - Colores de estado (éxito, advertencia, error, info)
   - Colores neutros para texto, fondos y bordes

2. **Sistema de Tipografía**
   - Familias de fuentes (principal, secundaria, monoespaciada)
   - Tamaños de fuente (desde xs hasta 3xl)
   - Pesos de fuente
   - Alturas de línea

3. **Sistema de Espaciado**
   - Unidad base de espaciado
   - Escala de espaciados derivados de la unidad base
   - Márgenes y paddings consistentes

4. **Sistema de Bordes y Radios**
   - Estilos de borde
   - Radios de borde para diferentes elementos
   - Sombras

### Requisitos

- Define todas las variables en el selector `:root`
- Organiza las variables por categorías con comentarios
- Implementa al menos 3 componentes que utilicen estas variables:
  - Botones (primario, secundario, de éxito, de advertencia)
  - Tarjetas/Cards
  - Alertas o notificaciones

### Ejemplo de Estructura Base

```css
:root {
    /* Sistema de Colores */
    --color-primary: #3498db;
    --color-secondary: #2ecc71;
    /* Añade el resto de variables... */
    
    /* Sistema de Tipografía */
    --font-family-primary: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    /* Añade el resto de variables... */
    
    /* Sistema de Espaciado */
    --spacing-unit: 0.25rem;
    /* Añade el resto de variables... */
    
    /* Sistema de Bordes */
    --border-radius-sm: 0.25rem;
    /* Añade el resto de variables... */
}

/* Ahora implementa los componentes usando estas variables */
```

## Ejercicio 2: Implementación de Metodología BEM

Para este ejercicio, rediseña una página web simple (como una landing page) utilizando la metodología BEM.

### Requisitos

1. La página debe incluir los siguientes componentes:
   - Encabezado con logo, navegación y botón de contacto
   - Sección hero con título, subtítulo e imagen
   - Sección de características con tarjetas/cards
   - Sección de testimonios
   - Formulario de contacto
   - Pie de página con enlaces y copyright

2. Sigue estrictamente la nomenclatura BEM:
   - Bloques: Componentes independientes
   - Elementos: Partes de un bloque (con doble guion bajo `__`)
   - Modificadores: Variantes o estados (con doble guion `-­-`)

3. Combina BEM con las variables CSS del ejercicio 1

### Ejemplo de Estructura BEM

```html
<header class="header">
    <div class="header__logo">
        <!-- Logo aquí -->
    </div>
    <nav class="header__nav">
        <ul class="nav">
            <li class="nav__item nav__item--active">
                <a href="#" class="nav__link">Inicio</a>
            </li>
            <!-- Más items... -->
        </ul>
    </nav>
    <button class="header__button button button--primary">Contacto</button>
</header>

<!-- Continúa con el resto de la página... -->
```

```css
.header {
    background-color: var(--color-background);
    padding: calc(var(--spacing-unit) * 4);
}

.header__logo {
    height: 50px;
}

.nav__item--active {
    border-bottom: 2px solid var(--color-primary);
}

/* Continúa con el resto de los estilos... */
```

## Ejercicio 3: Tema Claro/Oscuro con Variables CSS

Crea un sistema de cambio de tema claro/oscuro utilizando variables CSS y JavaScript.

### Requisitos

1. Define dos conjuntos de variables:
   - Variables para el tema claro (predeterminado)
   - Variables para el tema oscuro

2. Implementa un botón o interruptor que permita al usuario cambiar entre los temas

3. Usa JavaScript para:
   - Cambiar las variables CSS al hacer clic en el interruptor
   - Guardar la preferencia del usuario en `localStorage`
   - Cargar la preferencia guardada al cargar la página

4. Asegúrate de que todos los componentes se vean bien en ambos temas

### Ejemplo de Implementación

```css
:root {
    /* Tema claro (predeterminado) */
    --color-background: #ffffff;
    --color-text: #333333;
    --color-primary: #3498db;
    /* Más variables... */
}

[data-theme="dark"] {
    --color-background: #222222;
    --color-text: #f0f0f0;
    --color-primary: #5dade2;
    /* Más variables... */
}

body {
    background-color: var(--color-background);
    color: var(--color-text);
    transition: background-color 0.3s ease, color 0.3s ease;
}

/* Resto de estilos... */
```

```javascript
// Script para cambiar el tema
const themeToggle = document.querySelector('.theme-toggle');
const prefersDarkScheme = window.matchMedia('(prefers-color-scheme: dark)');

// Función para establecer el tema
function setTheme(isDark) {
    if (isDark) {
        document.documentElement.setAttribute('data-theme', 'dark');
        localStorage.setItem('theme', 'dark');
    } else {
        document.documentElement.setAttribute('data-theme', 'light');
        localStorage.setItem('theme', 'light');
    }
}

// Inicializar el tema
const savedTheme = localStorage.getItem('theme');
if (savedTheme) {
    setTheme(savedTheme === 'dark');
} else {
    setTheme(prefersDarkScheme.matches);
}

// Escuchar el clic en el botón
themeToggle.addEventListener('click', () => {
    const isDarkTheme = document.documentElement.getAttribute('data-theme') === 'dark';
    setTheme(!isDarkTheme);
});
```

## Ejercicio 4: Atomic CSS y Utilidades

Crea un pequeño sistema de clases de utilidad inspirado en Tailwind CSS.

### Requisitos

1. Crea clases de utilidad para:
   - Márgenes y paddings (m-0, m-1, p-0, p-1, etc.)
   - Tamaños de texto (text-xs, text-sm, text-lg, etc.)
   - Colores de texto y fondo (text-primary, bg-secondary, etc.)
   - Flexbox (flex, flex-col, justify-center, items-center, etc.)
   - Grid (grid, grid-cols-2, gap-2, etc.)
   - Utilidades de posicionamiento (relative, absolute, etc.)

2. Diseña una página simple utilizando principalmente estas clases de utilidad

3. Combina este enfoque con componentes BEM para elementos más complejos

### Ejemplo de Clases de Utilidad

```css
/* Utilidades de espaciado */
.m-0 { margin: 0; }
.m-1 { margin: var(--spacing-1); }
.m-2 { margin: var(--spacing-2); }
/* etc. */

.p-0 { padding: 0; }
.p-1 { padding: var(--spacing-1); }
.p-2 { padding: var(--spacing-2); }
/* etc. */

/* Utilidades de texto */
.text-xs { font-size: var(--font-size-xs); }
.text-sm { font-size: var(--font-size-sm); }
/* etc. */

/* Utilidades de flexbox */
.flex { display: flex; }
.flex-col { flex-direction: column; }
.justify-center { justify-content: center; }
/* etc. */
```

```html
<div class="card p-4 m-2 bg-white">
    <h2 class="text-lg text-primary mb-2">Título de la tarjeta</h2>
    <p class="text-sm text-gray mb-4">Descripción de la tarjeta que utiliza clases de utilidad.</p>
    <div class="flex justify-between">
        <button class="btn btn--primary p-2">Aceptar</button>
        <button class="btn btn--secondary p-2">Cancelar</button>
    </div>
</div>
```

## Entrega

Para cada ejercicio, entrega:

1. Archivos HTML, CSS y JavaScript necesarios
2. Una breve explicación de tu enfoque y decisiones de diseño
3. Capturas de pantalla que muestren el resultado final

## Criterios de Evaluación

- **Uso correcto de variables CSS**: 25%
- **Implementación adecuada de la metodología elegida**: 25%
- **Coherencia del sistema de diseño**: 20%
- **Responsividad y usabilidad**: 15%
- **Código limpio y bien organizado**: 15%

## Recursos Útiles

- [A Complete Guide to CSS Custom Properties](https://css-tricks.com/a-complete-guide-to-custom-properties/)
- [BEM Methodology](https://getbem.com/)
- [SMACSS Documentation](http://smacss.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) 