# Práctica 5: Diseño Responsive

## Objetivos

- Aplicar técnicas de diseño responsive usando Media Queries
- Implementar layouts fluidos con unidades relativas
- Crear componentes que se adapten a diferentes dispositivos
- Practicar el enfoque mobile-first
- Optimizar contenido multimedia para diferentes tamaños de pantalla

## Ejercicio 1: Landing Page Responsive

Crea una landing page responsive para un producto o servicio ficticio siguiendo estos requisitos:

1. Implementa un enfoque mobile-first
2. Utiliza al menos 3 breakpoints diferentes (móvil, tablet, desktop)
3. Incluye los siguientes componentes que deben adaptarse a cada tamaño:
   - Menú de navegación (convertido a menú hamburguesa en móvil)
   - Hero section con imagen destacada
   - Sección de características con tarjetas/cards
   - Sección de testimonios
   - Formulario de contacto
   - Footer con enlaces y copyright

### Requisitos Técnicos

- Utiliza unidades relativas (%, rem, em, vh/vw) para todos los tamaños
- Implementa Flexbox y/o Grid para la disposición de elementos
- Optimiza todas las imágenes para diferentes resoluciones
- Asegúrate de que todos los textos sean legibles en cualquier dispositivo
- Utiliza variables CSS para colores, espaciados y tamaños de fuente

## Ejercicio 2: Convertir un Diseño Desktop en Responsive

Toma el siguiente diseño (solo para desktop) y adáptalo para que sea completamente responsive:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Dashboard - Versión Desktop</title>
    <style>
        /* Estilos actuales - NO responsivos */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .dashboard {
            display: flex;
        }
        
        .sidebar {
            width: 250px;
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            height: 100vh;
        }
        
        .main-content {
            padding: 20px;
            width: calc(100% - 250px);
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
        }
        
        .stats {
            display: flex;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background-color: #f8f9fa;
            border-radius: 5px;
            padding: 20px;
            width: 25%;
            margin-right: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .charts {
            display: flex;
        }
        
        .chart {
            width: 50%;
            height: 300px;
            background-color: #f8f9fa;
            margin-right: 20px;
            border-radius: 5px;
            padding: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        table, th, td {
            border: 1px solid #ddd;
        }
        
        th, td {
            padding: 15px;
            text-align: left;
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <div class="sidebar">
            <h2>Panel de Control</h2>
            <ul>
                <li>Dashboard</li>
                <li>Usuarios</li>
                <li>Productos</li>
                <li>Ventas</li>
                <li>Reportes</li>
                <li>Configuración</li>
            </ul>
        </div>
        <div class="main-content">
            <div class="header">
                <h1>Dashboard Principal</h1>
                <div class="search">
                    <input type="text" placeholder="Buscar...">
                </div>
            </div>
            <div class="stats">
                <div class="stat-card">
                    <h3>Usuarios</h3>
                    <p>1,245</p>
                </div>
                <div class="stat-card">
                    <h3>Productos</h3>
                    <p>342</p>
                </div>
                <div class="stat-card">
                    <h3>Ventas</h3>
                    <p>$15,432</p>
                </div>
                <div class="stat-card">
                    <h3>Conversiones</h3>
                    <p>24%</p>
                </div>
            </div>
            <div class="charts">
                <div class="chart">
                    <h3>Ventas por Mes</h3>
                    <!-- Aquí iría un gráfico -->
                    <div style="height: 200px; background-color: #e9ecef; text-align: center; padding-top: 80px;">
                        [Gráfico de Barras]
                    </div>
                </div>
                <div class="chart">
                    <h3>Categorías Populares</h3>
                    <!-- Aquí iría un gráfico -->
                    <div style="height: 200px; background-color: #e9ecef; text-align: center; padding-top: 80px;">
                        [Gráfico Circular]
                    </div>
                </div>
            </div>
            <div class="table-section">
                <h3>Últimas Transacciones</h3>
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Cliente</th>
                            <th>Fecha</th>
                            <th>Monto</th>
                            <th>Estado</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>#12345</td>
                            <td>Juan Pérez</td>
                            <td>12/05/2023</td>
                            <td>$120.00</td>
                            <td>Completado</td>
                        </tr>
                        <tr>
                            <td>#12346</td>
                            <td>María García</td>
                            <td>11/05/2023</td>
                            <td>$85.50</td>
                            <td>Pendiente</td>
                        </tr>
                        <tr>
                            <td>#12347</td>
                            <td>Carlos López</td>
                            <td>10/05/2023</td>
                            <td>$240.00</td>
                            <td>Completado</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
```

### Tareas de Conversión

1. Agrega el meta viewport adecuado en el `<head>`
2. Convierte el sidebar en un menú desplegable para móviles con un botón de "hamburguesa"
3. Haz que las tarjetas de estadísticas se apilen en móviles (1 columna) y se muestren en 2 columnas en tablets
4. Adapta los gráficos para que se apilen en dispositivos pequeños
5. Modifica la tabla para que sea legible en móviles (puedes usar técnicas como hacer scroll horizontal, apilar celdas, o mostrar cards en lugar de filas)
6. Implementa los breakpoints necesarios con media queries
7. Aplica un enfoque mobile-first

## Ejercicio 3: Componentes Responsivos

Desarrolla las siguientes componentes responsivos independientes:

1. **Galería de Imágenes**: 
   - En móviles: 1 imagen por fila
   - En tablets: 2 imágenes por fila
   - En desktop: 4 imágenes por fila

2. **Menú de Navegación**:
   - En móviles: Menú hamburguesa desplegable
   - En desktop: Enlaces horizontales con hover effect

3. **Tarjeta de Producto**:
   - En móviles: Imagen arriba, descripción abajo
   - En desktop: Imagen a la izquierda, descripción a la derecha

4. **Modal/Ventana Emergente**:
   - En móviles: Ocupar toda la pantalla
   - En desktop: Centrado con máximo 500px de ancho

## Ejercicio 4: Optimización de Imágenes Responsivas

Crea una página con imágenes responsivas utilizando:

1. El enfoque básico con CSS:
```css
img {
  max-width: 100%;
  height: auto;
}
```

2. El elemento `<picture>` con diferentes fuentes según el tamaño:
```html
<picture>
  <source media="(min-width: 992px)" srcset="imagen-grande.jpg">
  <source media="(min-width: 768px)" srcset="imagen-mediana.jpg">
  <img src="imagen-pequeña.jpg" alt="Descripción">
</picture>
```

3. El atributo srcset para diferentes densidades de píxeles:
```html
<img src="imagen-base.jpg" 
     srcset="imagen-1x.jpg 1x, imagen-2x.jpg 2x" 
     alt="Descripción">
```

Incluye ejemplos de cada uno con imágenes reales y compara sus ventajas y desventajas.

## Ejercicio 5: Proyecto de Dashboard Responsive

Crea un dashboard administrativo responsivo que incluya:

1. **Sidebar de navegación**:
   - Visible permanentemente en desktop
   - Oculto y accesible mediante botón en móviles

2. **Header con**:
   - Logo/Nombre
   - Buscador
   - Menú de usuario

3. **Contenido principal con**:
   - Widgets de estadísticas
   - Gráficos (pueden ser simulados)
   - Tabla de datos

4. **Características responsive**:
   - Diseño de 3 columnas en desktop
   - 2 columnas en tablets
   - 1 columna en móviles
   - Tabla responsiva (scroll horizontal o apilado)

### Criterios de Evaluación

- Correcta adaptación a todos los tamaños de pantalla
- Uso apropiado de Media Queries
- Implementación de técnicas Mobile-First
- Optimización de imágenes y recursos
- Usabilidad y funcionalidad en todos los dispositivos
- Limpieza y estructura del código
- Creatividad y estética visual

## Recursos

- [Google Responsive Web Design Basics](https://developers.google.com/web/fundamentals/design-and-ux/responsive/)
- [Can I Use](https://caniuse.com/) para verificar compatibilidad
- [MDN Media Queries](https://developer.mozilla.org/es/docs/Web/CSS/Media_Queries)
- [Responsive Images Community Group](https://responsiveimages.org/)
- [Chrome DevTools para diseño responsive](https://developers.google.com/web/tools/chrome-devtools/device-mode) 