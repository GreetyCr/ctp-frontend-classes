# Notas y Buenas Prácticas de HTML

Este documento contiene recomendaciones, consejos y buenas prácticas para el desarrollo HTML. Utilícelo como referencia para mantener un código limpio, eficiente y accesible.

## Buenas Prácticas Generales

### Estructura y Organización

1. **Usa la declaración DOCTYPE correcta**
   - Siempre incluye `<!DOCTYPE html>` al inicio del documento.

2. **Especifica el idioma**
   - Usa el atributo `lang` en el elemento HTML para mejorar accesibilidad y SEO.
   ```html
   <html lang="es">
   ```

3. **Incluye metadatos básicos**
   - Asegúrate de incluir `charset`, `viewport` y `title` en todas las páginas.
   ```html
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Título descriptivo de la página</title>
   ```

4. **Organiza tu código con indentación**
   - Utiliza 2 o 4 espacios para hacer el código más legible.
   - Mantén una estructura visual consistente.

5. **Separa en archivos**
   - Divide sitios grandes en múltiples archivos HTML.
   - Mantén componentes comunes (cabeceras, pies de página) consistentes.

### Semántica

1. **Usa elementos semánticos sobre divs genéricos**
   - Prefiere `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` en lugar de divs.

2. **Estructura jerárquica correcta**
   - Usa solo un `<h1>` por página.
   - Sigue una jerarquía lógica de encabezados (h1 → h2 → h3...).
   - No saltes niveles de encabezado.

3. **Utiliza listas adecuadamente**
   - Para menús de navegación, usa `<ul>` o `<ol>`.
   - Para definiciones, usa `<dl>`, `<dt>` y `<dd>`.

4. **No abuses de las etiquetas de formato**
   - Usa `<strong>` para importancia, no solo para negrita.
   - Usa `<em>` para énfasis, no solo para cursiva.
   - Delega el formato visual a CSS siempre que sea posible.

## Accesibilidad

1. **Textos alternativos descriptivos**
   - Todas las imágenes deben tener atributos `alt` significativos.
   ```html
   <img src="grafico-ventas.jpg" alt="Gráfico de ventas del primer trimestre 2023">
   ```
   - Para imágenes decorativas, usa `alt=""`.

2. **Formularios accesibles**
   - Asocia etiquetas con campos.
   ```html
   <label for="nombre">Nombre:</label>
   <input type="text" id="nombre" name="nombre">
   ```
   - Agrupa campos relacionados con `<fieldset>` y `<legend>`.
   - Proporciona instrucciones claras y mensajes de error.

3. **Contraste y tamaño de texto**
   - Asegura suficiente contraste entre texto y fondo.
   - Evita tamaños de texto muy pequeños.

4. **ARIA cuando sea necesario**
   - Usa atributos ARIA cuando los elementos nativos no sean suficientes.
   - Ejemplo: `aria-label`, `aria-describedby`, `aria-required`.

5. **Tablas accesibles**
   - Usa `<caption>`, `<th>` con `scope`, `<thead>`, `<tbody>` para tablas de datos.
   - No uses tablas para maquetación.

## Enlaces e Hipervínculos

1. **Textos descriptivos en enlaces**
   - Evita "click aquí" o "leer más" como único texto de enlace.
   - El texto del enlace debe describir el destino.

2. **Indica enlaces externos**
   - Usa `target="_blank"` para abrir en nueva pestaña.
   - Añade `rel="noopener noreferrer"` para enlaces externos por seguridad.
   ```html
   <a href="https://ejemplo.com" target="_blank" rel="noopener noreferrer">Sitio externo</a>
   ```

3. **Enlaces a documentos**
   - Indica el formato y tamaño cuando enlazas a documentos para descargar.
   ```html
   <a href="informe.pdf">Informe anual (PDF, 2.4MB)</a>
   ```

## Multimedia

1. **Proporciona alternativas**
   - Para vídeos, incluye subtítulos o transcripciones.
   - Para audio, ofrece transcripciones textuales.

2. **Atributos importantes**
   - Usa `controls` para permitir control de reproducción.
   - Considera `preload="none"` para mejorar rendimiento.
   - Especifica `width` y `height` en imágenes y videos para evitar reajustes.

3. **Formatos múltiples**
   - Proporciona diferentes formatos para compatibilidad entre navegadores.
   ```html
   <video controls>
     <source src="video.webm" type="video/webm">
     <source src="video.mp4" type="video/mp4">
     <p>Tu navegador no soporta video HTML5. <a href="video.mp4">Descarga el video</a>.</p>
   </video>
   ```

## Formularios

1. **Validación**
   - Usa validación nativa HTML5 cuando sea posible.
   - Proporciona patrones claros con ejemplos.
   ```html
   <input type="tel" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" placeholder="123-456-7890">
   ```

2. **Tipos de input correctos**
   - Usa el tipo adecuado: `email`, `tel`, `date`, `number`, etc.
   - Esto mejora la experiencia en dispositivos móviles.

3. **Accesibilidad en formularios**
   - Marca campos obligatorios tanto visualmente como con `required`.
   - Proporciona feedback para errores de validación.
   - Usa `autocomplete` para ayudar a rellenar información común.

## Rendimiento

1. **Optimiza imágenes**
   - Usa formatos modernos como WebP cuando sea posible.
   - Especifica `width` y `height` para evitar saltos de contenido.
   - Considera `loading="lazy"` para imágenes bajo el pliegue.

2. **Carga diferida**
   ```html
   <img src="imagen.jpg" loading="lazy" alt="Descripción">
   ```

3. **Minimiza el uso de scripts inline**
   - Prefiere archivos JavaScript externos.
   - Usa `defer` o `async` para scripts no críticos.

## Compatibilidad entre Navegadores

1. **Prueba en múltiples navegadores**
   - Asegúrate de probar en Chrome, Firefox, Safari y Edge.
   - Verifica la compatibilidad con [caniuse.com](https://caniuse.com).

2. **Proporciona alternativas**
   - Incluye contenido alternativo para características no soportadas.
   ```html
   <picture>
     <source srcset="imagen.webp" type="image/webp">
     <img src="imagen.jpg" alt="Descripción">
   </picture>
   ```

## Validación

1. **Valida tu HTML regularmente**
   - Usa el [Validador W3C](https://validator.w3.org).
   - Corrige errores y advertencias.

2. **HTML limpio**
   - Evita atributos obsoletos.
   - Cierra correctamente todas las etiquetas.
   - Usa comillas para todos los valores de atributos.

## Errores Comunes a Evitar

1. **Abuso de divs**
   - Usar `<div>` cuando existe un elemento semántico apropiado.

2. **Uso incorrecto de headings**
   - Usar encabezados solo para cambiar el tamaño de texto.
   - Saltarse niveles de encabezado.

3. **Anidación incorrecta**
   - Colocar elementos de bloque dentro de elementos inline.
   - Anidaciones no permitidas (p.ej., `<p>` dentro de otro `<p>`).

4. **Accesibilidad ignorada**
   - Imágenes sin texto alternativo.
   - Contraste insuficiente entre texto y fondo.
   - Formularios sin etiquetas apropiadas.

5. **Nombre de archivos**
   - Usar espacios o caracteres especiales en nombres de archivo.
   - Prefiere "pagina-contacto.html" sobre "página contacto.html".

## Herramientas Recomendadas

1. **Editores de código**
   - Visual Studio Code con extensiones HTML
   - Sublime Text
   - Atom

2. **Validación y Pruebas**
   - [W3C Validator](https://validator.w3.org)
   - [WAVE Web Accessibility Tool](https://wave.webaim.org)
   - [Lighthouse](https://developers.google.com/web/tools/lighthouse)
   - [HTML5 Outliner](https://gsnedders.html5.org/outliner/)

3. **Comprobación de Compatibilidad**
   - [Can I Use](https://caniuse.com)
   - BrowserStack
   - LambdaTest

## Recursos Adicionales

1. **Documentación**
   - [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/HTML)
   - [HTML Living Standard](https://html.spec.whatwg.org/)
   - [W3C HTML](https://www.w3.org/TR/html52/)

2. **Accesibilidad**
   - [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
   - [WebAIM](https://webaim.org/)

3. **Tutoriales y Guías**
   - [HTML.com](https://html.com/)
   - [HTML Dog](https://htmldog.com/) 