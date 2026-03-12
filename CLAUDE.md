# CLAUDE.md - AI 101 Guide

## Referencia Principal
- **Fuente de verdad:** [README.md](README.md) — contenido, estructura, herramientas, entregables
- **Estructura:** 2 módulos × 4 clases = 8 sesiones en 4 semanas
- **Formato:** 2.5h síncronas + 2h asíncronas por clase = 36h total
- **Lenguaje público:** "asistente IA" (catálogo). Internamente: "agente" (README, labs, facilitator)

---

## Convenciones por Archivo

Cada clase tiene 4 archivos en `curriculum/class-XX/`:

| Archivo | Propósito | Restricciones |
|---------|-----------|---------------|
| `README.md` | Resumen + preparación del estudiante | Estructura estándar, SIN tiempos por fase |
| `lab/README.md` | Guía de taller paso a paso | Máximo 200 líneas |
| `slides/README.md` | Presentación reveal.js | Mantener CSS actual |
| `facilitator/README.md` | Guía pedagógica para instructor | Incluye checkpoints con tiempos (~120 min) |

**Tiempos:** Estudiante ve 150 min (2.5h). Facilitador planifica 120 min de instrucción. Diferencia = buffer.

---

## Templates de Archivo

**README.md de clase:**
`> 📦 Módulo X: Clase Y de 4` → Título → Resumen → ¿Por qué te sirve? → ¿Qué haremos? (sin tiempos) → Objetivos (3-4) → Preparación → Herramientas

**lab/README.md:**
`# Lab XX: Mi [Título]` → Objetivo → Tiempo (60 min) → Setup → Partes (~20 min c/u) → Entregable → Bonus

**slides/README.md:**
Diapositivas separadas por `---`: Portada → Objetivo → Contenido → Demo → Lab time → Cierre + tarea

**facilitator/README.md:**
Preparación previa → Momentos clave → Errores comunes → Preguntas frecuentes → Tips

---

## Principios Pedagógicos

Al crear contenido de clase, aplicar estos 9 principios:

1. **MOTIVATION_FIRST** — "Por qué" y valor práctico ANTES de cualquier técnica. Demo de impacto.
2. **ONE_CONCEPT_PER_CLASS** — UN concepto principal. No mezclar temas.
3. **REAL_WORK_ONLY** — Tareas reales del estudiante, nunca ficticias. Entregable USABLE.
4. **VERIFIABLE_DELIVERABLE** — Screenshot, documento, link funcional. "Entendí" NO es entregable.
5. **EXPLICIT_DEPENDENCIES** — Declarar qué requiere de clases anteriores y qué habilita.
6. **MAX_TWO_NEW_TOOLS** — Máximo 2 herramientas nuevas por clase. 3+ = PROHIBIDO.
7. **PORTFOLIO_BY_DEFAULT** — Cada entregable ES pieza del portfolio. Sin tarea separada.
8. **ANTI_HYPE_ALWAYS** — Al menos 1 momento de limitaciones/errores por clase.
9. **COMPETITIVE_COLLABORATION** — Al menos 1 battle por módulo (mismo reto, votación de pares).

---

## Estilo

- **Idioma:** Español latinoamericano
- **Tono:** README=profesional, Lab=práctico/amigable, Slides=conversacional, Facilitator=mentor-a-mentor
- **Emojis:** Moderados, estratégicos
- **Títulos de Lab:** Primera persona ("Mi") para ownership
- **Encoding:** UTF-8 puro. Tildes directas (á, é, í, ó, ú, ñ). Si aparece `�` = corrupto.

---

## Fuente de Verdad

**README.md es la única fuente de verdad.** Al modificar contenido: actualizar README.md primero, los demás referencian a él.

---

## Skills

| Comando | Genera |
|---------|--------|
| `/module-planner` | MODULE-PLAN.md |
| `/class-readme` | README.md de clase |
| `/class-lab` | lab/README.md |
| `/class-slides` | slides/README.md |
| `/class-facilitator` | facilitator/README.md |
| `/module-test` | test/README.md (clases 4, 8) |
| `/evaluation-class` | Reporte de calidad |
| `/lint-markdown` | Validación Markdown + enlaces |

**Flujo:** `/module-planner` → por clase: `/class-readme` → `/class-lab` → `/class-slides` → `/class-facilitator` → `/evaluation-class` → `/lint-markdown` → sincronizar README.md raíz

---

## Commits

Formato: `tipo: descripción concisa`
Types: `feat:` `fix:` `docs:` `refactor:` `style:`
