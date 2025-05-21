# Práctica 7: Animaciones y Transiciones en CSS

## Objetivos

- Implementar transiciones CSS para mejorar la experiencia de usuario
- Crear animaciones complejas con keyframes
- Controlar el tiempo y ritmo de las animaciones
- Aplicar transformaciones 2D y 3D
- Crear efectos interactivos para elementos de interfaz

## Ejercicio 1: Botones Interactivos con Transiciones

Crea una colección de botones interactivos que utilicen transiciones CSS para mejorar la experiencia del usuario.

### Requisitos

1. Diseña al menos 5 botones diferentes con los siguientes estados:
   - Estado normal
   - Estado hover
   - Estado active (cuando se hace clic)
   - Estado focus (para accesibilidad)
   - Estado disabled (opcional)

2. Cada botón debe implementar al menos 3 tipos diferentes de transiciones:
   - Cambio de color de fondo/texto
   - Transformación (escala, rotación, etc.)
   - Cambio en sombras o bordes
   - Efecto de "ripple" (ondulación)
   - Animación de íconos dentro del botón

3. Las transiciones deben ser suaves y mejorar la experiencia del usuario

### Ejemplo de un Botón con Transiciones

```css
.btn-pulse {
    background-color: #3498db;
    color: white;
    padding: 12px 24px;
    border: none;
    border-radius: 4px;
    font-weight: bold;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.btn-pulse:hover {
    background-color: #2980b9;
    transform: translateY(-3px);
    box-shadow: 0 6px 10px rgba(0, 0, 0, 0.2);
}

.btn-pulse:active {
    transform: translateY(0);
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.btn-pulse:focus {
    outline: none;
    box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.3);
}

.btn-pulse:disabled {
    background-color: #bdc3c7;
    cursor: not-allowed;
    transform: none;
    box-shadow: none;
}
```

## Ejercicio 2: Animaciones con @keyframes

Crea una página que muestre diferentes tipos de animaciones utilizando @keyframes.

### Requisitos

1. Implementa al menos 5 animaciones diferentes:
   - Animación de carga (spinner o progress bar)
   - Animación de entrada (fade-in, slide-in, etc.)
   - Animación de atención (pulso, rebote, etc.)
   - Animación continua (rotación, ondulación, etc.)
   - Animación secuencial (varios elementos animados en secuencia)

2. Para cada animación, controla las siguientes propiedades:
   - Duración (`animation-duration`)
   - Función de tiempo (`animation-timing-function`)
   - Retardo (`animation-delay`) cuando sea relevante
   - Iteraciones (`animation-iteration-count`)
   - Dirección (`animation-direction`) cuando sea relevante

3. Al menos una animación debe ser controlada por JavaScript (iniciar/detener)

### Ejemplo de Animación con @keyframes

```css
/* Animación de pulso */
@keyframes pulse {
    0% {
        transform: scale(1);
        opacity: 1;
    }
    50% {
        transform: scale(1.1);
        opacity: 0.8;
    }
    100% {
        transform: scale(1);
        opacity: 1;
    }
}

.pulse-element {
    width: 100px;
    height: 100px;
    background-color: #e74c3c;
    border-radius: 50%;
    animation: pulse 2s ease infinite;
}

/* Animación de carga */
@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.loader {
    width: 40px;
    height: 40px;
    border: 4px solid #f3f3f3;
    border-top: 4px solid #3498db;
    border-radius: 50%;
    animation: spin 1s linear infinite;
}
```

## Ejercicio 3: Card Flip 3D

Crea un componente de tarjeta que se voltee en 3D para mostrar información en ambos lados.

### Requisitos

1. Diseña una tarjeta con:
   - Un lado frontal con imagen y título
   - Un lado trasero con descripción y botón/enlace
   - Efecto de volteo 3D al hacer hover o clic (elige uno)

2. Implementa el efecto usando:
   - `transform-style: preserve-3d`
   - `perspective`
   - `backface-visibility`
   - Rotación 3D con `transform: rotateY()`
   - Transición suave entre estados

3. Crea al menos 3 variantes de la tarjeta con diferentes contenidos

### Ejemplo de Tarjeta 3D

```css
.flip-card {
    width: 300px;
    height: 400px;
    perspective: 1000px;
}

.flip-card-inner {
    width: 100%;
    height: 100%;
    transition: transform 0.8s;
    transform-style: preserve-3d;
    position: relative;
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.flip-card-front {
    background-color: #f1f1f1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.flip-card-back {
    background-color: #3498db;
    color: white;
    transform: rotateY(180deg);
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
```

## Ejercicio 4: Menú de Navegación Animado

Crea un menú de navegación con efectos de animación para mejorar la experiencia del usuario.

### Requisitos

1. Diseña un menú horizontal que incluya:
   - Al menos 5 items de navegación
   - Indicador visual para el item activo/hover
   - Transición fluida del indicador entre items
   - Efecto de despliegue para submenús (si los incluyes)

2. El menú debe incluir:
   - Animación de indicador (línea, fondo, etc.) al hacer hover
   - Efecto de transición para el estado activo
   - Animación para dispositivos móviles (menú hamburguesa)

3. Para versión móvil:
   - Animación del ícono hamburguesa a X (o similar)
   - Transición suave al abrir/cerrar el menú
   - Animación secuencial de los items al mostrar el menú

### Ejemplo de Menú Animado

```css
.nav {
    display: flex;
    list-style: none;
    padding: 0;
    background-color: #2c3e50;
    margin: 0;
    position: relative;
}

.nav-item {
    padding: 15px 20px;
    position: relative;
}

.nav-link {
    color: white;
    text-decoration: none;
    font-weight: 500;
    position: relative;
    padding: 5px 0;
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #3498db;
    transition: width 0.3s ease;
}

.nav-item:hover .nav-link::after {
    width: 100%;
}

.nav-item.active .nav-link::after {
    width: 100%;
    background-color: #e74c3c;
}

/* Versión móvil - Hamburguesa */
.hamburger {
    display: none;
    flex-direction: column;
    cursor: pointer;
    padding: 10px;
}

.hamburger-line {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 3px 0;
    transition: all 0.3s ease;
}

@media (max-width: 768px) {
    .hamburger {
        display: flex;
    }
    
    .nav {
        flex-direction: column;
        position: absolute;
        top: 60px;
        left: 0;
        right: 0;
        background-color: #2c3e50;
        height: 0;
        overflow: hidden;
        transition: height 0.3s ease;
    }
    
    .nav.open {
        height: auto;
    }
    
    .nav-item {
        opacity: 0;
        transform: translateY(-10px);
        transition: all 0.3s ease;
    }
    
    .nav.open .nav-item {
        opacity: 1;
        transform: translateY(0);
    }
    
    .nav.open .nav-item:nth-child(1) { transition-delay: 0.1s; }
    .nav.open .nav-item:nth-child(2) { transition-delay: 0.2s; }
    .nav.open .nav-item:nth-child(3) { transition-delay: 0.3s; }
    .nav.open .nav-item:nth-child(4) { transition-delay: 0.4s; }
    .nav.open .nav-item:nth-child(5) { transition-delay: 0.5s; }
    
    .hamburger.active .hamburger-line:nth-child(1) {
        transform: translateY(9px) rotate(45deg);
    }
    
    .hamburger.active .hamburger-line:nth-child(2) {
        opacity: 0;
    }
    
    .hamburger.active .hamburger-line:nth-child(3) {
        transform: translateY(-9px) rotate(-45deg);
    }
}
```

## Ejercicio 5: Animación de Scroll con Intersection Observer

Crea una página con elementos que se animen al hacer scroll, utilizando la API Intersection Observer.

### Requisitos

1. Crea una página con varias secciones, donde cada sección tenga elementos que se animen al entrar en el viewport

2. Implementa diferentes tipos de animaciones para los elementos:
   - Fade-in desde diferentes direcciones
   - Efecto de zoom
   - Revelación secuencial de elementos
   - Efectos de paralaje

3. Utiliza la API Intersection Observer para controlar cuándo se activan las animaciones

4. Las animaciones deben verse fluidas y mejorar la experiencia de usuario sin ser excesivas

### Ejemplo de Código con Intersection Observer

```css
/* Estilos para animaciones */
.fade-in {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.6s ease, transform 0.6s ease;
}

.fade-in.visible {
    opacity: 1;
    transform: translateY(0);
}

.fade-in-left {
    opacity: 0;
    transform: translateX(-50px);
    transition: opacity 0.6s ease, transform 0.6s ease;
}

.fade-in-left.visible {
    opacity: 1;
    transform: translateX(0);
}

.zoom-in {
    opacity: 0;
    transform: scale(0.8);
    transition: opacity 0.6s ease, transform 0.6s ease;
}

.zoom-in.visible {
    opacity: 1;
    transform: scale(1);
}
```

```javascript
// Configurar Intersection Observer
const animatedElements = document.querySelectorAll('.fade-in, .fade-in-left, .zoom-in');

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('visible');
        } else {
            // Opcional: quitar la clase cuando sale del viewport
            // entry.target.classList.remove('visible');
        }
    });
}, {
    threshold: 0.1, // El elemento se considera visible cuando el 10% está en el viewport
    rootMargin: '0px 0px -50px 0px' // Activa la animación un poco antes de llegar al borde inferior
});

animatedElements.forEach(element => {
    observer.observe(element);
});
```

## Entrega

Para cada ejercicio, entrega:

1. Archivos HTML, CSS y JavaScript necesarios
2. Una breve explicación de las técnicas de animación utilizadas
3. Capturas de pantalla o grabaciones que muestren las animaciones en acción

## Criterios de Evaluación

- **Implementación técnica correcta**: 25%
- **Creatividad y diseño visual**: 25%
- **Fluidez y suavidad de las animaciones**: 20%
- **Experiencia de usuario y propósito de las animaciones**: 15%
- **Código limpio y bien organizado**: 15%

## Recursos Útiles

- [MDN: Usando Transiciones CSS](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
- [MDN: Usando Animaciones CSS](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [MDN: Usando la API Intersection Observer](https://developer.mozilla.org/es/docs/Web/API/Intersection_Observer_API)
- [CSS Tricks: Guía de Transformaciones CSS](https://css-tricks.com/almanac/properties/t/transform/)
- [Web.dev: Principios de Animación para la Web](https://web.dev/articles/animations-guide) 