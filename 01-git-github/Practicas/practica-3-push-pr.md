# Práctica 3: Subiendo a GitHub y Creando Pull Requests

## Objetivo

Aprender a trabajar con repositorios remotos en GitHub, subir cambios y gestionar pull requests.

## Enunciado

Sube el repositorio local a GitHub, crea una rama de funcionalidad, haz cambios, crea un pull request, revisa los cambios y realiza la fusión desde la interfaz web de GitHub.

## Requisitos previos

- Tener Git instalado y configurado
- Tener una cuenta en GitHub
- Comprender los comandos básicos de Git

## Pasos Detallados

### 1. Crear un repositorio en GitHub

1. Inicia sesión en tu cuenta de GitHub
2. Haz clic en el botón "+" en la esquina superior derecha y selecciona "New repository"
3. Asigna un nombre descriptivo al repositorio (por ejemplo, "mi-proyecto-git")
4. Puedes añadir una descripción opcional
5. Mantén el repositorio como público para que sea más fácil compartirlo
6. No inicialices el repositorio con ningún archivo (sin README, .gitignore o licencia)
7. Haz clic en "Create repository"

### 2. Preparar tu repositorio local

Si ya tienes un repositorio local (como el de las prácticas anteriores), puedes utilizarlo. Si no, crea uno siguiendo estos pasos:

```bash
# Crear directorio para el proyecto
mkdir mi-proyecto-git
cd mi-proyecto-git

# Inicializar repositorio Git
git init

# Crear un archivo README.md básico
echo "# Mi Proyecto Git" > README.md
echo "" >> README.md
echo "Este es un proyecto de práctica para aprender a usar Git y GitHub." >> README.md

# Añadir y hacer commit del archivo
git add README.md
git commit -m "Commit inicial con README"
```

### 3. Conectar tu repositorio local con el remoto

Reemplaza `TU_USUARIO` con tu nombre de usuario de GitHub y `mi-proyecto-git` con el nombre que hayas elegido para tu repositorio:

```bash
git remote add origin https://github.com/TU_USUARIO/mi-proyecto-git.git
```

### 4. Subir tu repositorio local a GitHub

```bash
git push -u origin main
```

> **Nota**: Si tu rama principal se llama "master" en lugar de "main", deberás usar `git push -u origin master`.

### 5. Crear una nueva rama para una funcionalidad

```bash
git checkout -b feature/pagina-contacto
```

### 6. Añadir una nueva página de contacto

Crea un nuevo archivo llamado `contacto.html` con el siguiente contenido:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contacto - Mi Proyecto</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        h1 {
            color: #333;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }
        form {
            margin-top: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        input, textarea {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .menu {
            margin-bottom: 20px;
        }
        .menu a {
            margin-right: 15px;
            text-decoration: none;
            color: #0066cc;
        }
    </style>
</head>
<body>
    <div class="menu">
        <a href="index.html">Inicio</a>
        <a href="contacto.html">Contacto</a>
    </div>
    
    <h1>Contacto</h1>
    
    <p>Puedes contactarnos utilizando el formulario a continuación:</p>
    
    <form action="#" method="post">
        <div>
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required>
        </div>
        
        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>
        
        <div>
            <label for="mensaje">Mensaje:</label>
            <textarea id="mensaje" name="mensaje" rows="5" required></textarea>
        </div>
        
        <button type="submit">Enviar mensaje</button>
    </form>
    
    <p>También puedes contactarnos por email a: <a href="mailto:ejemplo@dominio.com">ejemplo@dominio.com</a></p>
</body>
</html>
```

### 7. Crear un archivo índice simple si no lo tienes ya

Si aún no tienes un archivo `index.html`, créalo con el siguiente contenido:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Proyecto Git</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        h1 {
            color: #333;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }
        .menu {
            margin-bottom: 20px;
        }
        .menu a {
            margin-right: 15px;
            text-decoration: none;
            color: #0066cc;
        }
    </style>
</head>
<body>
    <div class="menu">
        <a href="index.html">Inicio</a>
        <a href="contacto.html">Contacto</a>
    </div>
    
    <h1>Bienvenido a Mi Proyecto</h1>
    
    <p>Este es un proyecto de práctica para aprender a usar Git y GitHub.</p>
    
    <h2>¿Qué aprenderás?</h2>
    <ul>
        <li>Comandos básicos de Git</li>
        <li>Trabajo con repositorios remotos</li>
        <li>Creación y gestión de ramas</li>
        <li>Fusión de cambios</li>
        <li>Creación de Pull Requests</li>
    </ul>
</body>
</html>
```

### 8. Hacer commit de los cambios en la rama de funcionalidad

```bash
git add contacto.html
git add index.html  # Si lo has creado ahora
git commit -m "Añadida página de contacto y menú de navegación"
```

### 9. Subir la rama de funcionalidad a GitHub

```bash
git push -u origin feature/pagina-contacto
```

### 10. Crear un Pull Request en GitHub

1. Ve a tu repositorio en GitHub
2. Verás un mensaje que indica que has subido recientemente una rama. Haz clic en "Compare & pull request"
3. Alternativamente, puedes ir a la pestaña "Pull requests" y hacer clic en "New pull request"
4. Asegúrate de que la rama base sea `main` y la rama a comparar sea `feature/pagina-contacto`
5. Añade un título descriptivo para el pull request, por ejemplo: "Añadir página de contacto"
6. En la descripción, explica los cambios realizados:
   ```
   Esta pull request añade:
   - Una nueva página de contacto con un formulario
   - Un menú de navegación en ambas páginas
   - Estilos CSS básicos para ambas páginas
   
   Los cambios están listos para revisión.
   ```
7. Haz clic en "Create pull request"

### 11. Revisar el Pull Request

1. Observa la interfaz del pull request
2. Explora las pestañas "Conversation", "Commits" y "Files changed"
3. En "Files changed", puedes hacer comentarios específicos sobre líneas individuales de código
4. Puedes dejar un comentario general en la pestaña "Conversation"

### 12. Fusionar el Pull Request

1. Una vez que estés satisfecho con los cambios, haz clic en el botón "Merge pull request"
2. Confirma la fusión haciendo clic en "Confirm merge"
3. Verás un mensaje indicando que la rama ha sido fusionada y puede ser eliminada
4. Puedes eliminar la rama haciendo clic en "Delete branch"

### 13. Actualizar tu repositorio local

Vuelve a tu repositorio local y actualiza la rama principal:

```bash
git checkout main
git pull origin main
```

### 14. Eliminar la rama local una vez que ya no sea necesaria

```bash
git branch -d feature/pagina-contacto
```

## Verificación

Para comprobar que has completado la práctica correctamente, deberías:

1. Tener un repositorio en GitHub con al menos dos archivos: `README.md` e `index.html` (y posiblemente `contacto.html`)
2. Ver el historial de pull requests en tu repositorio de GitHub, con al menos uno fusionado
3. Tener tu repositorio local actualizado con todos los cambios

## Reto adicional

1. Crea una nueva rama llamada `feature/estilos`
2. Añade un archivo `styles.css` con estilos mejorados para tu sitio
3. Modifica los archivos HTML para que utilicen este archivo CSS externo en lugar de estilos internos
4. Sube la rama y crea un nuevo pull request
5. Pide a un compañero que revise tu pull request y haga comentarios
6. Realiza cambios basados en los comentarios recibidos
7. Fusiona el pull request cuando esté listo 