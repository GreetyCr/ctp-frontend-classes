# Práctica 2: Creación de un Blog Personal

## Objetivo
Diseñar y estructurar un blog personal con múltiples entradas utilizando HTML5 semántico.

## Descripción
En esta práctica crearás la estructura de un blog personal completo con varias entradas y secciones. El enfoque principal será implementar correctamente los elementos semánticos de HTML5 para crear un sitio bien estructurado y accesible.

## Requisitos
1. El blog debe constar de al menos 3 páginas HTML:
   - Página principal (índice) con las entradas más recientes
   - Página individual para una entrada completa
   - Página "Acerca de" con información del autor

2. Todas las páginas deben compartir la misma estructura:
   - Cabecera con título del blog y navegación principal
   - Contenido principal
   - Barra lateral con información complementaria
   - Pie de página con información de contacto

3. Implementación obligatoria de elementos semánticos:
   - `<header>` para la cabecera del sitio
   - `<nav>` para la navegación
   - `<main>` para el contenido principal
   - `<article>` para cada entrada del blog
   - `<section>` para dividir el contenido
   - `<aside>` para la barra lateral
   - `<footer>` para el pie de página
   - `<time>` para fechas de publicación

4. Elementos adicionales:
   - Enlaces internos entre las diferentes páginas
   - Enlaces a redes sociales (pueden ser ficticios)
   - Al menos una lista de categorías o etiquetas
   - Una imagen por cada entrada con atributos adecuados
   - Un formulario de comentarios en la página de entrada individual
   - Uso adecuado de `<figure>` y `<figcaption>` para las imágenes

## Estructura Sugerida

### Página Principal (index.html)
1. **Cabecera**
   - Título del blog
   - Navegación principal (Inicio, Categorías, Acerca de)

2. **Contenido Principal**
   - Resumen de 3-5 entradas recientes
   - Cada entrada debe incluir:
     - Título (enlace a la página individual)
     - Fecha de publicación
     - Imagen destacada
     - Resumen del contenido
     - Enlace "Leer más"

3. **Barra Lateral**
   - Perfil breve del autor
   - Categorías del blog
   - Enlaces de interés

4. **Pie de Página**
   - Información de contacto
   - Copyright
   - Enlaces a redes sociales

### Página de Entrada Individual (articulo.html)
1. **Contenido del artículo completo**
   - Título
   - Información del autor y fecha
   - Contenido completo con párrafos, subtítulos, listas, etc.
   - Imágenes con leyendas
   
2. **Sección de comentarios**
   - Comentarios existentes (al menos 2 ejemplos)
   - Formulario para añadir nuevo comentario

### Página Acerca de (acerca.html)
1. **Información detallada del autor**
   - Biografía extendida
   - Foto
   - Habilidades o intereses
   - Historial o trayectoria

## Consejos
- Utiliza contenido real o ficticio que sea coherente
- Organiza tu código con indentación adecuada
- Usa comentarios HTML para identificar las secciones principales
- Asegúrate de que la navegación funcione correctamente entre todas las páginas
- Verifica que tus páginas sean accesibles (uso adecuado de alt, tabindex, etc.)

## Entrega
1. Todos los archivos HTML del blog
2. Carpeta con las imágenes utilizadas
3. Documento breve explicando tu enfoque y decisiones de estructura

## Criterios de Evaluación
- Implementación correcta de la semántica HTML5
- Estructura coherente y navegación funcional
- Accesibilidad y buenas prácticas
- Organización y legibilidad del código
- Creatividad y coherencia del contenido 