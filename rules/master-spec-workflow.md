# Master Spec Workflow

Este documento define la metodología unificada para gestión de especificaciones, evitando over-engineering y manteniendo un enfoque práctico y eficiente.

---

## 📂 Organización de directorios

```

specs/
├── docs/
│   └── context.md           # Contexto completo del proyecto (Paso obligatorio, se genera la primera vez que se corre el Master Spec Workflow)
├── features/                    # Features complejas con fases
│   ├── 000-feature/
│   │   ├── 000-feature-spec.md  # Spec completa con fases incluidas
│   │   ├── 000-user-story.md
│   │   └── 000-acceptance-criteria.md
├── tasks/                      # Tasks simples (una sola fase)
│   ├── 001-rename-package.md
│   ├── 002-update-dependencies.md
│   └── 003-fix-bug-login.md
├── status/
│   ├── in-progress/           # Features/tasks en desarrollo
│   └── done/                  # Features/tasks completadas
├── changelog/                 # Logs de cambios
└── templates/                 # Plantillas
```

---

## 🎯 Criterios de clasificación

### **Features complejas** → `/features/` (Metodología con fases)
- Nuevas funcionalidades que requieren múltiples componentes
- Cambios arquitectónicos significativos
- Integraciones complejas con APIs externas
- Refactoring mayor que afecta múltiples módulos

### **Tasks simples** → `/tasks/` (Una sola fase)
- Cambios menores en código existente
- Actualizaciones de dependencias
- Fixes de bugs específicos
- Renombrado de archivos/paquetes
- Mejoras menores de UX/UI

---

## 📋 Flujo de trabajo unificado

### **Para Features complejas (Metodología con fases)**

1. **Crear estructura**: `features/000-feature/`
2. **Definir spec completa**: `000-feature-spec.md` con:
   - Objetivo general
   - User stories
   - Acceptance criteria
   - **Fases de implementación** (cada fase = una tarea)
3. **Status tracking**: Mover a `status/in-progress/` al comenzar
4. **Implementación por fases**:
   - Ejecutar Fase 1
   - **Verificar y confirmar** antes de avanzar
   - Ejecutar Fase 2
   - **Verificar y confirmar** antes de avanzar
   - Continuar hasta completar todas las fases
5. **Changelog**: Documentar cambios en `changelog/000-feature-log.md`
6. **Completar**: Mover a `status/done/` al finalizar

### **Para Tasks simples (Una sola fase)**

1. **Crear spec completa**: `tasks/001-[nombre-descriptivo].md` con:
   - Objetivo claro del cambio
   - Alcance y limitaciones
   - Dependencias identificadas
   - **Una sola fase de implementación**
   - Criterios de éxito medibles
2. **Status tracking**: Mover a `status/in-progress/` al comenzar
3. **Implementar**: Seguir la fase única
4. **Completar**: Mover a `status/done/` al finalizar

---

## 🔄 Proceso de especificación y confirmación (OBLIGATORIO)

**Para CUALQUIER task o feature, SIEMPRE seguir este proceso:**

### **Paso 0: Contexto del Proyecto (OBLIGATORIO)**
1. ✅ **Revisar `docs/context.markdown`** para entender:
   - Arquitectura del sistema
   - Dependencias y tecnologías
   - Estructura de carpetas
   - Contexto del negocio
   - Stakeholders y restricciones
   - Design system y componentes
2. ✅ **Tomar contexto completo** antes de generar cualquier spec

### **Paso 1: Generación de Spec**
1. ✅ **Crear especificación completa** con planificación detallada
2. ✅ **Incluir objetivos, alcance, dependencias y criterios de éxito**
3. ✅ **Definir fases de implementación** claras y medibles
4. ✅ **NO resumir** el contenido en la respuesta

### **Paso 2: Confirmación obligatoria**
1. ✅ **Avisar** que la spec está lista para revisión
2. ✅ **Esperar confirmación explícita** del usuario
3. ✅ **Solo entonces** proceder con la implementación

### **Paso 3: Implementación por fases**
1. ✅ **Ejecutar una fase** según especificación
2. ✅ **Verificar implementación** y chequear errores
3. ✅ **Preguntar explícitamente** si avanzar a la siguiente fase
4. ✅ **Esperar confirmación** antes de continuar
5. ✅ **Repetir** hasta completar todas las fases

---

## 📝 Convenciones de nombres

### **Features complejas**
- ID numérico único: `000`, `001`, `002`...
- Archivos: `000-feature-spec.md`, `000-user-story.md`, `000-acceptance-criteria.md`
- **Fases incluidas en el spec**: No archivos separados

### **Tasks simples**
- Numeración secuencial: `001-`, `002-`, `003`...
- Formato: `001-[nombre-descriptivo].md`
- **Una sola fase** en el spec

---

## 📊 Tipos de especificaciones

### **Refactoring**
- Renombrar paquetes y archivos
- Actualizar dependencias
- Reorganizar estructura de código

### **Infraestructura**
- Configuración de servicios externos
- Extensión de tipos y esquemas
- Validación de datos

### **Nuevas funcionalidades**
- Implementación de features
- Integración de APIs
- Mejoras de UX/UI

### **Testing y calidad**
- Tests de integración
- Actualización de exports
- Validación end-to-end

---

## 🔧 Comandos útiles

```bash
# Mover especificación completada
mv specs/tasks/001-spec-name.md specs/status/done/
mv specs/features/000-feature/ specs/status/done/

# Verificar estado
ls specs/tasks/
ls specs/features/
ls specs/status/in-progress/
ls specs/status/done/

# Crear changelog
touch specs/changelog/000-feature-log.md
```

---

## 📈 Sistema de changelog

**Solo para features complejas** (tasks simples no requieren changelog):

Formato estándar en `changelog/000-feature-log.md`:

| Fecha      | Autor    | Cambio realizado                                       | Estado           |
| ---------- | -------- | ------------------------------------------------------ | ---------------- |
| 2025-01-15 | [nombre] | Completada Fase 1: Configuración inicial              | ⏳ [in-progress] |
| 2025-01-16 | [nombre] | Completada Fase 2: Implementación core                | ✅ [done]        |

---

## 🎯 Criterios de decisión rápida

**¿Es una feature compleja?**
- ✅ Requiere múltiples archivos modificados
- ✅ Afecta la arquitectura del proyecto
- ✅ Necesita testing extensivo
- ✅ Involucra múltiples stakeholders

**¿Es una task simple?**
- ✅ Cambio puntual en código existente
- ✅ Una sola funcionalidad específica
- ✅ Fix de bug o mejora menor
- ✅ Actualización de configuración

**⚠️ IMPORTANTE**: Independientemente del tipo, **SIEMPRE** se debe generar una especificación completa con fases de implementación antes de ejecutar cualquier task.

---

## 🔄 Flujo resumido

### **Feature compleja:**
1. **Revisar contexto** → `docs/context.md`
2. Crear → `features/000-feature/`
3. Spec completa con fases incluidas
4. Confirmación obligatoria del usuario
5. Mover a `status/in-progress/`
6. **Implementar Fase 1** → Verificar → Confirmar avance
7. **Implementar Fase 2** → Verificar → Confirmar avance
8. **Continuar fases** hasta completar
9. Documentar en changelog
10. Mover a `status/done/`

### **Task simple:**
1. **Revisar contexto** → `docs/context.md` 
2. Crear spec completa → `tasks/001-[nombre].md` (una sola fase)
3. Confirmación obligatoria del usuario
4. Mover a `status/in-progress/`
5. Implementar fase única
6. Mover a `status/done/`

---

## ✨ Ventajas del workflow simplificado

- 🎯 **Sin over-engineering**: Fases dentro del spec, no archivos separados
- 📊 **Trazabilidad**: Completa para features, simple para tasks
- 🔄 **Confirmación por fases**: Control granular del progreso
- 📝 **Documentación**: Proporcional a la complejidad
- 🚀 **Eficiencia**: Una sola spec por feature con fases incluidas
- 🏗️ **Robustez**: Metodología completa para cambios complejos
- ⚡ **Agilidad**: Menos archivos que mantener
- 🎛️ **Control**: Confirmación explícita entre fases