# Base Spec Template

Este archivo describe la metodología **Spec Driven Development (SDD)** aplicada en este proyecto.  
Todas las especificaciones (specs) deben seguir estas reglas para garantizar claridad, trazabilidad y mejora continua.

---

## 📂 Organización de directorios

specs/
├── features/
│ ├── 000-feature/
│ │ ├── 000-feature-spec.md
│ │ ├── 000-user-story.md
│ │ ├── 000-acceptance-criteria.md
│ │ └── ...
├── tasks/
├── status/
│ ├── in-progress/
│ └── done/
├── changelog/
└── templates/

-   **`features/000-feature/`**: Cada feature tiene que tener un **ID numérico único** (`000`, `001`, `002`...), usado en todos los archivos relacionados. Todos aquellos features recientemente creados almacenarlos en `features`.

-**`tasks/`**: Cada conjunto de tareas debe organizarse en una **subcarpeta con el mismo ID del feature** al que pertenecen, los nombres de cada task tienen que hacer alusión a lo que van a resolver, por ejemplo:
tasks/
├── 000-feature/
│ ├── 000-000-configuracion-inicial.md
│ ├── 000-001-setup-base-datos.md
│ └── ...
├── 001-feature/
│ ├── 001-001-formulario-registro.md
│ ├── 001-002-sistema-login.md
│ └── ...

-   El prefijo del archivo (`000-001-[nombre-descriptivo].md`) indica:

    -   `000`: ID del feature.
    -   `001`: ID de la tarea dentro del feature.
    -   `[nombre-descriptivo]`: Nombre que hace alusión a lo que va a resolver la tarea.

-   Cada tarea debe documentar:
    -   Propósito.
    -   Inputs y outputs esperados.
    -   Criterios de éxito.
    -   Relación con user stories y acceptance criteria correspondientes.

Esto asegura trazabilidad entre **feature → user stories → acceptance criteria → tasks**.

-   **`status/`**: Cada spec debe reflejar su estado (cuando se indique explícitamente que se quiere empezar a trabajar un feature, pasarlo por completo a la carpeta `in-progress` y al cumplir con todos los puntos de cada spec, pasar el feature a la carpeta `done`).

-   **`changelog/`**: Ante cualquier cambio en una spec, se debe crear un archivo log con el mismo nombre de la spec + sufijo `-log`.
    -   Ejemplo: `000-feature-spec.md` → `changelog/000-feature-spec-log.md`.

---

## 📑 Pasos de Spec Driven Development

### 1. Crear la **Base Spec**

-   Describir **objetivo general** del proyecto o módulo.
-   Incluir requisitos funcionales y no funcionales.
-   Identificar dependencias iniciales.

### 2. Definir **Feature Specs**

-   Cada feature tiene un archivo con numeración (`000-feature-spec.md`).
-   Debe incluir:
    -   Nombre del feature.
    -   Descripción funcional.
    -   Alcance.
    -   Dependencias.
    -   Enlaces a user stories y criterios de aceptación.

### 3. Redactar **User Stories**

-   Cada historia debe estar en un archivo separado.
-   Estructura: _Como [rol] quiero [objetivo] para [beneficio]_.
-   Relacionada explícitamente con el feature ID.

### 4. Definir **Acceptance Criteria**

-   Para cada user story, definir criterios de éxito claros, medibles y verificables.
-   Cada criterio va numerado y versionado.

### 5. Desglose en **Tareas**

-   Convertir cada criterio en tareas técnicas.
-   Documentar inputs, outputs y casos límite.

### 6. **Status Tracking**

-   Cada **feature** debe ser movido a `in-progress`, o `done` según avance.

### 7. **Changelog**

-   Cada actualización genera un archivo en `changelog/`.
-   Ejemplo: `000-feature-spec.md` → `000-feature-spec-log.md`.
-   El log debe incluir:
    -   Fecha del cambio.
    -   Autor.
    -   Comentario sobre la modificación.

### 8. **Retroalimentación continua**

-   Cada vez que una spec se lea y detecte inconsistencias, **mejorarla en el momento**.
-   Iterar sobre la misma sin perder trazabilidad (todo cambio documentado en `changelog/`).

-   Cada vez que una spec se vuelva a leer y se detecte una inconsistencia, ambigüedad o punto de mejora:

1. **Actualizar la spec directamente** en su archivo original (ej: `000-feature-spec.md`).
2. **Registrar la mejora en el changelog correspondiente** (`changelog/000-feature-spec-log.md`) siguiendo el formato estándar.
3. **Revisar trazabilidad**: asegurar que el cambio también esté reflejado en user stories, acceptance criteria, tareas o tests asociados.
4. **Iterar**: si la mejora genera nuevas ideas o requisitos, documentarlos como nuevas entradas en la misma spec.

De esta forma, cada iteración mantiene la trazabilidad y evita pérdida de información.

-   Cada vez que una spec sea modificada, se debe crear o actualizar un archivo en `changelog/` con el mismo nombre de la spec + sufijo `-log`.

El changelog debe seguir este **formato estándar**:

-   **Fecha**: en formato `YYYY-MM-DD`.
-   **Autor**: quien realizó la modificación.
-   **Cambio realizado**: descripción breve y clara.
-   **Estado anterior / nuevo**: opcional, para reflejar evolución dentro de `/status/`.

### 000-feature-spec

| Fecha      | Autor    | Cambio realizado                                       | Estado           |
| ---------- | -------- | ------------------------------------------------------ | ---------------- |
| 2025-09-21 | [nombre] | Ajustado criterio de aceptación #2 para mayor claridad | ⏳ [in-progress] |
| 2025-09-22 | [nombre] | Agregada nueva user story #003                         | ✅ [done]        |

Ejemplo:  
`000-feature-spec.md` → `changelog/000-feature-spec-log.md`

El changelog debe seguir este **formato estándar**:

---

## 🔄 Flujo resumido

1. Crear feature → `features/000-feature/`.
1. Añadir spec → `features/000-feature/000-feature-spec.md`.
1. Añadir user stories → `features/000-feature/000-user-story.md`.
1. Añadir criterios de aceptación → `features/000-feature/000-acceptance-criteria.md`.
1. Desglosar en tareas → `tasks/000-feature/000-000-[nombre-descriptivo].md`.
1. Actualizar status en `/status/`.
1. Documentar cambios en `/changelog/000-feature-log.md`.
1. Revisar, iterar, mejorar specs de forma continua.

---
