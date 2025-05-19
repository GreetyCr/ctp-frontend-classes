# Práctica 2: Trabajando con Ramas

## Objetivo

Aprender a crear y fusionar ramas en Git, así como resolver conflictos básicos que pueden surgir durante el proceso de fusión.

## Enunciado

Crea una rama `feature/boton`, agrega un botón en `index.html`, fusiónala a la rama principal y resuelve cualquier conflicto que surja.

## Requisitos previos

- Tener Git instalado y configurado
- Conocimientos básicos de comandos Git
- Conocimientos básicos de HTML

## Pasos Detallados

### 1. Crear y preparar el repositorio

```bash
# Crear directorio para el proyecto
mkdir practica-ramas
cd practica-ramas

# Inicializar repositorio Git
git init

# Crear archivo index.html inicial
touch index.html
```

### 2. Añadir contenido inicial al archivo index.html

Abre el archivo `index.html` en tu editor favorito y añade el siguiente contenido:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Ramas Git</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .contenido {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi Página Web</h1>
    </header>
    <div class="contenido">
        <h2>Bienvenido</h2>
        <p>Esta es una página de ejemplo para practicar ramas en Git.</p>
    </div>
</body>
</html>
```

### 3. Hacer commit del contenido inicial

```bash
git add index.html
git commit -m "Contenido inicial de la página"
```

### 4. Crear una nueva rama para la característica del botón

```bash
git checkout -b feature/boton
```

Este comando crea una nueva rama llamada `feature/boton` y cambia a ella automáticamente.

### 5. Modificar el archivo en la nueva rama

Ahora, edita el archivo `index.html` para añadir un botón. Añade el siguiente código justo después del párrafo en la sección de contenido:

```html
<button id="saludar">¡Haz clic aquí!</button>
<script>
    document.getElementById('saludar').addEventListener('click', function() {
        alert('¡Hola desde la rama feature/boton!');
    });
</script>
```

El archivo debería verse así:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Ramas Git</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .contenido {
            margin-top: 20px;
        }
        button {
            background-color: #008CBA;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #005f73;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi Página Web</h1>
    </header>
    <div class="contenido">
        <h2>Bienvenido</h2>
        <p>Esta es una página de ejemplo para practicar ramas en Git.</p>
        <button id="saludar">¡Haz clic aquí!</button>
        <script>
            document.getElementById('saludar').addEventListener('click', function() {
                alert('¡Hola desde la rama feature/boton!');
            });
        </script>
    </div>
</body>
</html>
```

### 6. Hacer commit de los cambios en la rama feature/boton

```bash
git add index.html
git commit -m "Añadido botón interactivo con JavaScript"
```

### 7. Volver a la rama principal y hacer un cambio que generará conflicto

```bash
git checkout main
```

En la rama principal, modifica también el archivo `index.html`, pero de forma diferente. Cambia el color del encabezado y añade un párrafo adicional:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Ramas Git</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            background-color: #9C27B0; /* Cambio de color */
            color: white;
            padding: 10px;
            text-align: center;
        }
        .contenido {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi Página Web</h1>
    </header>
    <div class="contenido">
        <h2>Bienvenido</h2>
        <p>Esta es una página de ejemplo para practicar ramas en Git.</p>
        <p>Hemos modificado el color del encabezado y añadido este párrafo en la rama principal.</p>
    </div>
</body>
</html>
```

### 8. Hacer commit de los cambios en la rama principal

```bash
git add index.html
git commit -m "Cambiado color de encabezado y añadido párrafo adicional"
```

### 9. Intentar fusionar la rama feature/boton en la rama principal

```bash
git merge feature/boton
```

Esto generará un conflicto porque ambas ramas han modificado el mismo archivo en las mismas áreas.

### 10. Resolver el conflicto

Abre el archivo `index.html` en tu editor. Verás que Git ha marcado las áreas en conflicto de la siguiente manera:

```
<<<<<<< HEAD
... (cambios de la rama actual)
=======
... (cambios de la rama que estás fusionando)
>>>>>>> feature/boton
```

Debes editar manualmente el archivo para resolver el conflicto, combinando ambos cambios de la forma que desees. Una solución podría ser:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Práctica de Ramas Git</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            background-color: #9C27B0; /* Mantenemos el color de la rama principal */
            color: white;
            padding: 10px;
            text-align: center;
        }
        .contenido {
            margin-top: 20px;
        }
        button {
            background-color: #008CBA;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #005f73;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi Página Web</h1>
    </header>
    <div class="contenido">
        <h2>Bienvenido</h2>
        <p>Esta es una página de ejemplo para practicar ramas en Git.</p>
        <p>Hemos modificado el color del encabezado y añadido este párrafo en la rama principal.</p>
        <button id="saludar">¡Haz clic aquí!</button>
        <script>
            document.getElementById('saludar').addEventListener('click', function() {
                alert('¡Hola desde la página fusionada!');
            });
        </script>
    </div>
</body>
</html>
```

Guarda el archivo con los conflictos resueltos.

### 11. Completar la fusión

Una vez resuelto el conflicto, debes marcarlo como resuelto y completar la fusión:

```bash
git add index.html
git commit -m "Fusionada rama feature/boton y resuelto conflicto"
```

### 12. Verificar el historial

```bash
git log --graph --oneline --all
```

Este comando mostrará una representación gráfica del historial de commits, incluyendo las ramificaciones y fusiones.

## Verificación

Para comprobar que has completado la práctica correctamente, deberías:

1. Tener dos ramas en tu repositorio: `main` y `feature/boton`
2. La rama `main` debería contener todos los cambios fusionados
3. El archivo `index.html` debería incluir tanto el botón como el párrafo adicional
4. Al abrir `index.html` en un navegador, deberías ver el botón y, al hacer clic en él, debería mostrarse una alerta

## Reto adicional

1. Crea una nueva rama `feature/footer` para agregar un pie de página
2. Implementa el pie de página con información de contacto
3. Fusiona esta rama con la rama principal
4. Crea una rama `hotfix/button-color` para cambiar el color del botón
5. Implementa el cambio y fusiona esta rama también 