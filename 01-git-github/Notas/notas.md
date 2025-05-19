# Notas y Buenas Prácticas de Git y GitHub

Este documento recopila consejos, trucos y buenas prácticas para trabajar con Git y GitHub que te ayudarán a mantener una base de código limpia y colaborativa.

## Convenciones de nomenclatura para ramas

Utilizar nombres descriptivos y estructurados para las ramas facilita la organización y comprensión del flujo de trabajo:

- `main` o `master`: Rama principal con código estable y listo para producción.
- `develop`: Rama de desarrollo con los últimos cambios integrados.
- `feature/nombre-caracteristica`: Para nuevas funcionalidades.
- `bugfix/descripcion-problema`: Para corrección de errores.
- `hotfix/descripcion-urgente`: Para correcciones urgentes que van directamente a producción.
- `release/version`: Para preparar lanzamientos.
- `docs/descripcion`: Para cambios en documentación.

Ejemplo: `feature/login-form` o `bugfix/header-responsive`

## Mensajes de commit claros y efectivos

Un buen mensaje de commit debe:

1. Tener una primera línea breve (50 caracteres máximo) que resuma el cambio
2. Usar el modo imperativo: "Añade", "Corrige", "Actualiza" (no "Añadido", "Corregido")
3. Explicar el "qué" y "por qué" en lugar del "cómo"

Estructura recomendada:
```
<tipo>: <descripción breve>

<explicación detallada opcional>

<referencia a issues relacionados opcional>
```

Tipos comunes:
- `feat`: Nueva característica
- `fix`: Corrección de error
- `docs`: Cambios en documentación
- `style`: Cambios de formato, no funcionales
- `refactor`: Reescritura de código sin cambiar funcionalidad
- `test`: Añade o corrige pruebas
- `chore`: Tareas de mantenimiento, dependencias, etc.

Ejemplo:
```
feat: añade validación de formulario de registro

Implementa validación del lado del cliente para el formulario de registro 
usando la biblioteca Validator.js. Incluye verificación de:
- Formato de email
- Fuerza de contraseña
- Coincidencia de campos de contraseña

Closes #45
```

## Uso responsable de .gitignore

Un archivo `.gitignore` bien configurado evita el seguimiento de archivos innecesarios:

- Archivos de configuración personal
- Archivos generados automáticamente
- Dependencias y paquetes
- Archivos temporales
- Archivos con información sensible

Ejemplo básico de `.gitignore` para proyectos web:
```
# Dependencias
node_modules/
vendor/

# Archivos compilados
dist/
build/
*.min.js

# Archivos de ambiente
.env
.env.local

# Logs
*.log
npm-debug.log*

# Archivos del sistema
.DS_Store
Thumbs.db

# Archivos de IDE/editores
.idea/
.vscode/
*.swp
*.swo
```

## Estrategias de ramificación

Considera adoptar una estrategia de ramificación según las necesidades del proyecto:

1. **Git Flow**: Estructura formal con ramas de desarrollo, características, lanzamientos y hotfixes.
   - Ideal para proyectos con ciclos de lanzamiento planificados
   - Puede ser complejo para equipos pequeños

2. **GitHub Flow**: Enfoque más simple basado en ramas de características y pull requests.
   - Ideal para despliegue continuo
   - Más ágil y fácil de adoptar

3. **Trunk-Based Development**: Desarrollo principalmente en la rama principal con ramas cortas.
   - Favorece la integración continua
   - Requiere buenas prácticas de testing y feature flags

## Recomendaciones adicionales

- **Haz commits pequeños y frecuentes**: Facilita encontrar errores y comprender la evolución del código
- **Pull/Fetch antes de Push**: Siempre actualiza tu copia local antes de enviar cambios
- **Usa Pull Requests**: Incluso en proyectos personales, ayudan a revisar tu propio código
- **Aprende comandos avanzados**: `git rebase`, `git stash`, `git cherry-pick` son herramientas poderosas
- **Utiliza aliases**: Configura aliases en Git para comandos frecuentes para ahorrar tiempo 