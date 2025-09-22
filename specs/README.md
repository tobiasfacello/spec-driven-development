# Spec Driven Development - Ejemplos

Este directorio contiene ejemplos de archivos siguiendo la metodología **Spec Driven Development (SDD)**. Los archivos de ejemplo demuestran cómo estructurar y documentar especificaciones, historias de usuario, criterios de aceptación, tareas y cambios.

## 📂 Estructura de Ejemplos Creados

```
specs/
├── features/
│   └── 001-user-authentication/
│       ├── 001-feature-spec.md          # Especificación del feature
│       ├── 001-user-story.md            # Historia de usuario
│       └── 001-acceptance-criteria.md   # Criterios de aceptación
├── status/
│   ├── in-progress/
│   │   └── 002-dashboard-feature-spec.md  # Feature en progreso
│   └── done/
│       └── 000-initial-setup-feature-spec.md  # Feature completado
├── changelog/
│   ├── 001-feature-spec-log.md          # Log de cambios del feature 001
│   └── 002-feature-spec-log.md          # Log de cambios del feature 002
├── tasks/
│   ├── 001-user-authentication/
│   │   ├── 001-001-formulario-registro.md    # Tarea: Formulario de registro
│   │   ├── 001-002-sistema-login.md          # Tarea: Sistema de login
│   │   └── 001-003-recuperacion-contraseña.md # Tarea: Recuperación de contraseña
│   └── 002-dashboard/
│       └── 002-001-widget-estadisticas.md   # Tarea: Widget de estadísticas
└── templates/
    ├── base-spec-template.md            # Plantilla base de metodología
    ├── feature-spec-template.md         # Plantilla de especificación de feature
    ├── user-story-template.md           # Plantilla de historia de usuario
    └── acceptance-criteria-template.md   # Plantilla de criterios de aceptación
```

## 🎯 Ejemplos Incluidos

### Features de Ejemplo

1. **001 - Sistema de Autenticación de Usuarios** (Pending)

    - Registro de usuarios
    - Inicio de sesión
    - Recuperación de contraseña
    - Validación de seguridad

2. **002 - Dashboard de Usuario** (In-progress)

    - Widgets personalizables
    - Estadísticas de usuario
    - Notificaciones en tiempo real
    - Diseño responsive

3. **000 - Configuración Inicial del Sistema** (Done)
    - Configuración de base de datos
    - Variables de entorno
    - Estructura de directorios
    - Scripts de inicialización

### Tareas de Ejemplo

-   **001-001-formulario-registro**: Implementar formulario de registro
-   **001-002-sistema-login**: Implementar sistema de login
-   **001-003-recuperacion-contraseña**: Implementar recuperación de contraseña
-   **002-001-widget-estadisticas**: Crear widget de estadísticas de usuario

### Changelogs de Ejemplo

-   Logs de cambios para features 001 y 002
-   Ejemplos de evolución de especificaciones
-   Registro de mejoras y actualizaciones

## 📋 Cómo Usar Estos Ejemplos

1. **Para Nuevos Features**: Usa los templates en `/templates/` como base
2. **Para Seguimiento**: Mueve features entre carpetas de `/status/` según progreso
3. **Para Tareas**: Crea tareas en `/tasks/` siguiendo la numeración del feature
4. **Para Cambios**: Documenta modificaciones en `/changelog/`

## 🔄 Flujo Recomendado

1. Crear feature spec usando template
2. Definir user stories relacionadas
3. Establecer acceptance criteria
4. Desglosar en tareas técnicas
5. Mover a `in-progress` cuando se inicie desarrollo
6. Documentar cambios en changelog
7. Mover a `done` cuando se complete

## 📝 Notas Importantes

-   Todos los archivos siguen la numeración establecida en la metodología SDD
-   Los ejemplos incluyen casos de prueba y consideraciones técnicas
-   Se mantiene trazabilidad entre features, user stories, acceptance criteria y tasks
-   Los changelogs documentan la evolución de las especificaciones

---

_Estos ejemplos sirven como referencia para implementar la metodología Spec Driven Development en tu proyecto._
