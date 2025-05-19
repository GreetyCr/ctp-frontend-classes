# Práctica 1: Inicializar un Repositorio

## Objetivo

Crear un repositorio local y realizar una serie de commits para familiarizarse con los comandos básicos de Git.

## Enunciado

Crea un repositorio local, realiza 3 commits con cambios en un archivo HTML `hola.html`.

## Pasos Detallados

### 1. Crear una carpeta para el proyecto

```bash
mkdir mi-primer-proyecto
cd mi-primer-proyecto
```

### 2. Inicializar el repositorio Git

```bash
git init
```

Deberías ver un mensaje confirmando que se ha inicializado un repositorio Git vacío.

### 3. Crear el archivo HTML inicial

Crea un archivo llamado `hola.html` con el siguiente contenido:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página</title>
</head>
<body>
    <h1>¡Hola Mundo!</h1>
</body>
</html>
```

### 4. Realizar el primer commit

```bash
git add hola.html
git commit -m "Primer commit: Estructura básica HTML"
```

### 5. Modificar el archivo para el segundo commit

Ahora, modifica el archivo `hola.html` para añadir un párrafo:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página</title>
</head>
<body>
    <h1>¡Hola Mundo!</h1>
    <p>Este es mi primer proyecto utilizando Git.</p>
</body>
</html>
```

### 6. Realizar el segundo commit

```bash
git add hola.html
git commit -m "Segundo commit: Añadido párrafo de descripción"
```

### 7. Modificar el archivo para el tercer commit

Finalmente, añade un poco de estilo al archivo:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            color: #333;
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #0066cc;
        }
    </style>
</head>
<body>
    <h1>¡Hola Mundo!</h1>
    <p>Este es mi primer proyecto utilizando Git.</p>
</body>
</html>
```

### 8. Realizar el tercer commit

```bash
git add hola.html
git commit -m "Tercer commit: Añadido estilo CSS básico"
```

### 9. Verificar los commits realizados

Para ver el historial de commits:

```bash
git log
```

Deberías ver los tres commits que has realizado, con sus respectivos mensajes, autor, fecha y hash.

## Verificación

Para comprobar que has completado la práctica correctamente, deberías:

1. Tener un repositorio Git inicializado
2. Tener un archivo `hola.html` con HTML, texto y CSS
3. Tener tres commits en tu historial

## Reto adicional

Si quieres practicar más, intenta:

1. Añadir un archivo `.gitignore` para excluir archivos temporales o específicos del sistema
2. Crear una rama llamada `feature/footer`, añadir un pie de página al HTML y hacer commit
3. Volver a la rama principal y hacer merge de la rama `feature/footer` 