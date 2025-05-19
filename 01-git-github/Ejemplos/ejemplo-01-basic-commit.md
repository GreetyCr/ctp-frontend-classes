# Ejemplo 1: Proceso Básico de Commit

En este ejemplo, visualizaremos el proceso básico de trabajo con Git, desde la creación de archivos hasta realizar un commit.

## Paso 1: Crear un archivo nuevo

Primero, creamos un archivo llamado `index.html` con un contenido básico:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mi Proyecto</title>
</head>
<body>
    <h1>Bienvenido a mi sitio web</h1>
    <p>Esta es la página principal de mi proyecto.</p>
</body>
</html>
```

## Paso 2: Verificar el estado del repositorio

Al ejecutar `git status`, vemos que el archivo aparece como "untracked" (no rastreado):

```
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)
```

## Paso 3: Añadir el archivo al área de staging

Usamos `git add` para poner el archivo en el área de staging (preparación):

```
$ git add index.html
```

## Paso 4: Verificar el estado nuevamente

Ahora el archivo aparece como "Changes to be committed" (cambios para ser confirmados):

```
$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
```

## Paso 5: Realizar el commit

Confirmamos los cambios preparados con un mensaje descriptivo:

```
$ git commit -m "Añadido archivo index.html con estructura básica"
[main (root-commit) f7d2a3c] Añadido archivo index.html con estructura básica
 1 file changed, 10 insertions(+)
 create mode 100644 index.html
```

## Paso 6: Verificar el historial de commits

Podemos ver el commit que acabamos de crear:

```
$ git log
commit f7d2a3c82a4f9876543210fedcba98765432abcd (HEAD -> main)
Author: Tu Nombre <tu@email.com>
Date:   Mar 10 2023 12:34:56 -0600

    Añadido archivo index.html con estructura básica
```

## Diagrama del proceso

```
┌─────────────┐    git add     ┌─────────────┐    git commit    ┌─────────────┐
│  Workspace  │ ─────────────> │  Staging    │ ───────────────> │  Repositorio │
│  (Archivos) │                │  Area       │                  │  (Historial) │
└─────────────┘                └─────────────┘                  └─────────────┘

     ↑                               │                               │
     │                               │                               │
     │                               │                               │
     └───────────────────────────────┴───────────────────────────────┘
                     Acciones para mover entre áreas
                     (git checkout, git reset, etc.)
```

## Explicación detallada

1. **Workspace (área de trabajo)**: Es donde modificas archivos en tu proyecto. Git no rastrea automáticamente estos cambios.

2. **Staging Area (área de preparación)**: Es un área intermedia donde indicas a Git qué cambios quieres incluir en tu próximo commit. Esto te permite hacer commits parciales y organizados.

3. **Repositorio (historial)**: Cuando haces un commit, los cambios en staging se guardan permanentemente en el historial de Git.

Este flujo de trabajo básico es fundamental y lo utilizarás constantemente en todos tus proyectos con Git. 