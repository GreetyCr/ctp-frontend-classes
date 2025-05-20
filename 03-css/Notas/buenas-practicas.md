# Buenas Prácticas en CSS

El desarrollo CSS eficiente requiere seguir ciertas prácticas que mejoran la mantenibilidad, rendimiento y escalabilidad del código. A continuación, se presentan las mejores prácticas organizadas por categorías:

## Organización del Código

1. **Estructura coherente**: Organiza tu CSS siguiendo un patrón consistente:
   ```css
   /* 1. Variables/Custom Properties */
   :root {
     --primary-color: #3b82f6;
   }

   /* 2. Reset/Normalize */
   * {
     box-sizing: border-box;
     margin: 0;
     padding: 0;
   }

   /* 3. Elementos base */
   body {
     font-family: 'Helvetica', sans-serif;
   }

   /* 4. Layout/Componentes */
   .container { ... }
   
   /* 5. Utilidades */
   .text-center { ... }
   ```

2. **Comentarios descriptivos**: Utiliza comentarios para explicar secciones y decisiones importantes:
   ```css
   /* ==========================================================================
      Sección de Navegación Principal
      ========================================================================== */
   ```

3. **Archivos separados**: Para proyectos grandes, divide tu CSS en múltiples archivos:
   - `reset.css`
   - `typography.css`
   - `layout.css`
   - `components.css`
   - `utilities.css`

4. **Utiliza un preprocesador**: SASS/SCSS permiten organizar mejor el código con nesting, variables, mixins y parciales.

## Selectores y Especificidad

1. **Evita selectores demasiado específicos**: Cuanto más específico sea un selector, más difícil será anularlo.
   ```css
   /* Evitar */
   body header nav ul li a.link { ... }
   
   /* Preferir */
   .nav-link { ... }
   ```

2. **Evita el uso excesivo de `!important`**: Utilízalo solo como último recurso y documenta por qué fue necesario.

3. **Utiliza selectores de clase en lugar de ID**: Las clases son reutilizables y tienen menor especificidad.

4. **Evita selectores de atributo cuando sea posible**: Son más lentos que los selectores de clase.

5. **Limita la anidación**: No anides más de 3 niveles de profundidad para mantener la especificidad baja.

## Rendimiento

1. **Minimiza el uso de selectores descendientes**: Especialmente los que tienen comodines.
   ```css
   /* Evitar */
   .sidebar * { ... }
   
   /* Preferir */
   .sidebar-item { ... }
   ```

2. **Evita las propiedades que causan repintado/reflujo**: Propiedades como `box-shadow`, `border-radius`, `position`, `float`, etc., son costosas para el rendimiento.

3. **Optimiza las media queries**: Combina las media queries para los mismos breakpoints.

4. **Minifica y comprime para producción**: Utiliza herramientas como `cssnano` o `clean-css`.

5. **Utiliza `will-change` con prudencia**: Informa al navegador de transformaciones futuras, pero su uso excesivo puede ser contraproducente.

## Nomenclatura y Convenciones

1. **Sigue una metodología de nomenclatura**: BEM, SMACSS, o OOCSS.

   **Ejemplo BEM (Block Element Modifier):**
   ```css
   /* Bloque */
   .card { ... }
   
   /* Elemento */
   .card__title { ... }
   
   /* Modificador */
   .card--featured { ... }
   ```

2. **Utiliza nombres semánticos**: Nombra clases basadas en su propósito, no en su apariencia.
   ```css
   /* Evitar */
   .big-blue-button { ... }
   
   /* Preferir */
   .btn-primary { ... }
   ```

3. **Consistencia en la escritura**: Decide si usarás camelCase, kebab-case o snake_case y mantén la consistencia.

4. **Prefijos para diferentes tipos de componentes**:
   ```css
   .js-* /* para selectores usados por JavaScript */
   .l-* /* para layouts */
   .c-* /* para componentes */
   .u-* /* para utilidades */
   ```

## Reutilización y Mantenibilidad

1. **DRY (Don't Repeat Yourself)**: Utiliza variables o custom properties para valores recurrentes.
   ```css
   :root {
     --primary-color: #3b82f6;
     --spacing-unit: 8px;
     --font-heading: 'Roboto', sans-serif;
   }
   ```

2. **Crea componentes modulares**: Diseña componentes independientes que no dependan de su ubicación.

3. **Utiliza clases de utilidad**: Para propiedades comunes y repetitivas.
   ```css
   .text-center { text-align: center; }
   .mt-2 { margin-top: 2rem; }
   ```

4. **Evita estilos en línea**: Dificultan el mantenimiento y aumentan la especificidad.

## Responsive y Accesibilidad

1. **Mobile-first**: Comienza con estilos para dispositivos móviles y luego agrega media queries para pantallas más grandes.
   ```css
   /* Estilo base para móviles */
   .container {
     width: 100%;
   }
   
   /* Tabletas y mayores */
   @media (min-width: 768px) {
     .container {
       width: 750px;
     }
   }
   ```

2. **Utiliza unidades relativas**: Prefiere `rem`, `em`, `%` en lugar de píxeles para mejorar la accesibilidad.
   ```css
   body {
     font-size: 16px; /* Base para cálculos rem */
   }
   
   h1 {
     font-size: 2rem; /* 32px en escala predeterminada */
   }
   ```

3. **Contraste adecuado**: Asegura que el texto tenga suficiente contraste con el fondo (relación mínima de 4.5:1).

4. **No deshabilites el zoom**: Nunca uses `user-scalable=no` en el viewport meta.

5. **Prueba con lectores de pantalla**: Asegúrate de que tu sitio sea navegable sin elementos visuales.

## Depuración y Calidad

1. **Utiliza linters**: Herramientas como `stylelint` ayudan a mantener la calidad del código.

2. **Revisa el CSS no utilizado**: Utiliza herramientas como PurgeCSS para eliminar reglas no utilizadas.

3. **Prueba en múltiples navegadores**: Considera usar autoprefixer para compatibilidad.

4. **Valida tu CSS**: Usa el validador de W3C para encontrar errores.

5. **Herramientas de inspección**: Utiliza las herramientas de desarrollador del navegador para identificar problemas.

## Frameworks y Bibliotecas

1. **Evalúa si realmente necesitas un framework**: A veces CSS vanilla es suficiente.

2. **Si usas un framework, conócelo bien**: Entender cómo funciona internamente te ayudará a personalizarlo mejor.

3. **Personaliza solo lo necesario**: Sobrescribir muchos estilos de un framework puede generar código redundante.

4. **Considera enfoques modernos**: Utility-first CSS (como Tailwind CSS) o CSS-in-JS dependiendo del proyecto.

## Recursos para Profundizar

- [MDN Web Docs - CSS](https://developer.mozilla.org/es/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [Smashing Magazine](https://www.smashingmagazine.com/category/css/)
- [Web.dev - CSS](https://web.dev/learn/css/)
- [A11Y Project - Accessible Colors](https://www.a11yproject.com/) 