# Ejemplo 2: Diagrama de Ramificación (Branching)

Este ejemplo muestra visualmente cómo funciona el proceso de ramificación y fusión en Git, con un diagrama ASCII y una explicación detallada.

## Diagrama de ramificación y fusión

```
           (F)─────(G)─────(H)  feature
          /               \
(A)───(B)───(C)───(D)───(E)───(I)───(J)  main
```

## Explicación del diagrama

1. **(A)**, **(B)**: Commits iniciales en la rama principal (`main`).
2. En el punto **(B)**, se crea una nueva rama llamada `feature`.
3. **(F)**, **(G)**, **(H)**: Desarrollo en la rama `feature`. Mientras tanto...
4. **(C)**, **(D)**, **(E)**: El desarrollo continúa también en la rama `main`.
5. En el punto **(H)** y **(E)**, ocurre una fusión (merge) de `feature` hacia `main`, creando el commit de fusión **(I)**.
6. **(J)**: El desarrollo continúa en la rama `main` después de la fusión.

## Comandos utilizados en este escenario

### 1. Creación de la rama `feature` en el punto B

```bash
git checkout -b feature
```

### 2. Desarrollo en la rama `feature` (commits F, G, H)

```bash
# Hacer cambios en archivos
git add .
git commit -m "Crear componente F"

# Más cambios
git add .
git commit -m "Añadir estilos G"

# Más cambios
git add .
git commit -m "Implementar funcionalidad H"
```

### 3. Mientras tanto, volver a `main` y continuar desarrollo (C, D, E)

```bash
git checkout main

# Hacer cambios
git add .
git commit -m "Actualizar documentación C"

# Más cambios
git add .
git commit -m "Corregir bug D"

# Más cambios
git add .
git commit -m "Optimizar rendimiento E"
```

### 4. Fusionar `feature` en `main`

```bash
git checkout main
git merge feature
```

### 5. Resolver posibles conflictos y crear commit de fusión (I)

```bash
# Si hay conflictos:
# 1. Editar archivos con conflictos
# 2. Marcar como resueltos
git add .
git commit  # Commit de fusión (I)
```

### 6. Continuar desarrollo en `main` (J)

```bash
# Hacer cambios
git add .
git commit -m "Implementar nueva funcionalidad J"
```

## Ejemplo de flujo de trabajo con ramas

Este patrón de desarrollo es muy común:

1. **Crear una rama para una nueva característica** - Aisla el desarrollo para no afectar el código principal.
2. **Desarrollar en esta rama** - Realizar varios commits para completar la característica.
3. **Mantener actualizada la rama principal** - Otros miembros del equipo siguen trabajando.
4. **Fusionar cuando la característica esté completa** - Incorporar los cambios al código principal.
5. **Continuar con nuevas características o mejoras** - El ciclo se repite.

Este flujo de trabajo permite desarrollar múltiples funcionalidades en paralelo, experimentar con ideas sin comprometer la estabilidad del código principal, y mantener un historial claro y organizado de los cambios realizados. 