# CLAUDE.md - AI 101 Guide

## Referencia Principal
- **Syllabus (fuente de verdad):** [context/course_syllabus.md](context/course_syllabus.md)
- **Propuesta comercial:** [context/propuesta_02.md](context/propuesta_02.md)
- **Estructura:** 2 módulos (8 clases en 4 semanas)
- **Formato:** 3h síncronas + 2h asíncronas por clase = 40h total

---

## Checklist de Progreso

### M1: Fundamentos + Primeros Superpoderes (Clases 1-4)
- [ ] **Clase 1:** El Nuevo Juego
- [ ] **Clase 2:** El Arte del Prompt
- [ ] **Clase 3:** Tu Copiloto de Contenido
- [ ] **Clase 4:** Research con IA: Gemini + Perplexity

### M2: Superpoderes Aplicados + Portfolio (Clases 5-8)
- [ ] **Clase 5:** Automatización sin código
- [ ] **Clase 6:** Tu Asistente IA Personalizado
- [ ] **Clase 7:** Portfolio + Caso de Éxito
- [ ] **Clase 8:** Presentación + Siguientes Pasos

---

## Convenciones por Archivo

Cada clase tiene 4 archivos en `curriculum/class-XX/`:

| Archivo | Propósito | Restricciones |
|---------|-----------|---------------|
| `README.md` | Resumen + preparación del estudiante | Estructura estándar |
| `lab/README.md` | Guía de taller paso a paso | Máximo 200 líneas |
| `slides/README.md` | Presentación reveal.js | Mantener CSS actual |
| `facilitator/README.md` | Guía pedagógica para instructor | Reflexiones profundas |

---

## Estructura de Archivos

### README.md (raíz de clase)
```markdown
> 📦 **Módulo X:** Clase Y de 4

# Título de la Clase

## Resumen (2-3 párrafos)
## Estructura sugerida (tabla de fases - 180 min)
## Objetivos de aprendizaje (3-4 items)
## Preparación para la clase
## Herramientas necesarias
```

### lab/README.md
```markdown
# Lab: Título

## Objetivo (1 párrafo)
## Tiempo estimado (60 min)
## Antes de empezar (setup)
## Parte 1, 2, 3... (~20 min c/u)
## Entregable
## Bonus (opcional)
```

### slides/README.md
```markdown
<!-- Diapositivas separadas por --- -->
- Portada
- Objetivo de hoy
- Contenido principal (múltiples slides)
- Demo en vivo
- Lab time
- Cierre + tarea
```

### facilitator/README.md
```markdown
# Guía del Facilitador: Tema

## Preparación previa
## Momentos clave de la clase
## Errores comunes de estudiantes
## Preguntas frecuentes
## Tips de facilitación
```

---

## Referencias de Estilo

- **Idioma:** Español latinoamericano
- **Tono general:** Empoderador, práctico, anti-hype
- **Tono README:** Profesional, inspirador
- **Tono Lab:** Práctico, paso a paso, amigable
- **Tono Slides:** Educativo, conversacional
- **Tono Facilitator:** Reflexivo, mentor-a-mentor
- **Emojis:** Moderados, estratégicos

---

## 💾 Sugerencias de Commit

```
📝 Sugerencia de commit:
git commit -m "tipo: descripción concisa"
```

**Formato:**
- `feat:` nueva funcionalidad
- `fix:` corrección de error
- `docs:` documentación
- `refactor:` reestructuración
- `style:` formato

---

## ⚠️ Reglas de Encoding (OBLIGATORIO)

**SIEMPRE usar UTF-8 puro para todos los archivos.**
- Tildes directas: á, é, í, ó, ú, ñ, ü
- Signos: ¿?, ¡!
- Si aparecen `�` o `\u00f3`, el archivo está corrupto

---

## ⚠️ Fuente de Verdad (OBLIGATORIO)

**context/course_syllabus.md es la fuente de verdad para:**
- Contenido de cada clase
- Estructura de módulos
- Entregables y tareas

**README.md (raíz) es la fuente de verdad pública para:**
- Descripción del curso
- Tabla de contenidos con links a clases
- Estado de progreso del curriculum

**Al modificar contenido:**
1. Actualizar primero `context/course_syllabus.md`
2. Sincronizar `README.md` (raíz) si cambia estructura o progreso
3. Los demás archivos referencian al syllabus

---

## Herramientas del Curso

| Herramienta | Propósito | Clase |
|-------------|-----------|-------|
| **Claude** | Asistente principal, contenido | 1-3 |
| **Gemini** | Gems, Deep Research | 4 |
| **Perplexity** | Spaces, fuentes verificables | 4 |
| **Make/Zapier** | Automatización sin código | 5 |
| **Notion** | Segundo cerebro + portfolio | 6 |

---

## Entregables por Clase

| Clase | Entregable |
|-------|------------|
| 1 | Screenshot resultado + reflexión |
| 2 | 3 prompts maestros |
| 3 | Contenido profesional publicable |
| 4 | Research doc + asistente configurado |
| 5 | 1 flujo automatizado |
| 6 | Asistente configurado |
| 7 | Caso de éxito publicable |
| 8 | Presentación + plan desarrollo |

---

## Skills Disponibles

| Skill | Comando | Genera |
|-------|---------|--------|
| Module Planner | `/module-planner` | MODULE-PLAN.md (arquitectura de módulo) |
| Class README | `/class-readme` | README.md de clase |
| Class Lab | `/class-lab` | lab/README.md |
| Class Slides | `/class-slides` | slides/README.md |
| Class Facilitator | `/class-facilitator` | facilitator/README.md |
| Module Test | `/module-test` | test/README.md + questions.md (clases 4, 8) |
| Evaluation Class | `/evaluation-class` | Reporte de calidad |
| Lint Markdown | `/lint-markdown` | Validación Markdown + enlaces |

### Flujo de Trabajo Recomendado

1. `/module-planner` para M1 o M2
2. Para cada clase:
   - `/class-readme` → `/class-lab` → `/class-slides` → `/class-facilitator`
3. Para clases 4 y 8: `/module-test`
4. `/evaluation-class` para verificar calidad
5. `/lint-markdown` antes de publicar
6. **Sincronizar README.md (raíz)** con tabla de contenidos actualizada

---

## Notas de Desarrollo

*Última actualización: 2026-01-23*

- Propuesta 02 aprobada: 8 clases en 4 semanas
- Nombre: "AI 101 - Desbloqueando el verdadero poder de la IA"
- Enfoque: Super-usuario de IA (no constructor)
- Duración: 40h total (24h sync + 16h async)
- Estructura de carpetas simplificada vs Code 301
- 8 skills de Claude Code creados para generación de contenido
