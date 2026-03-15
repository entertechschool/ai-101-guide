# AGENTS.md - AI 101 Guide

> Instrucciones para agentes AI que trabajan en este repositorio.
> Compatible con: Claude Code, GitHub Copilot, Cursor, Gemini CLI, Windsurf, Codex.

---

## Proyecto

Repositorio del curso **AI 101 — IA para Profesionales** de EnterTechSchool. Contiene curriculum completo: READMEs, laboratorios, slides, guías de facilitador y tests diagnósticos. 8 clases en 4 semanas para convertir profesionales en super-usuarios de IA.

---

## Fuente de Verdad

**`README.md` es la única fuente de verdad.** Contiene:

- Estructura del curso (2 módulos × 4 clases)
- Contenido clave y entregables por clase
- Sistema de evaluación (pesos, aprobación, asistencia)
- Formato, modalidad y herramientas

**Regla:** Leer SIEMPRE `README.md` antes de generar o modificar contenido. Nunca hardcodear información que ya está en el syllabus. Si hay conflicto entre un archivo de clase y `README.md`, el syllabus gana.

---

## Estructura del Repositorio

```
├── README.md                        # Syllabus (fuente de verdad)
├── AGENTS.md                        # Este archivo
├── CLAUDE.md                        # Configuración Claude Code
├── catalog.md                       # Sílabo académico / catálogo B2C
├── curriculum/
│   ├── class-{01..08}/              # Clases del curso
│   │   ├── README.md                # Resumen para estudiante
│   │   ├── lab/README.md            # Laboratorio paso a paso
│   │   ├── slides/README.md         # Presentación reveal.js
│   │   ├── facilitator/README.md    # Guía pedagógica
│   │   └── infographic/index.html   # Infografía post-clase (WhatsApp)
│   ├── module-1/                    # Plan del Módulo 1
│   └── module-2/                    # Plan del Módulo 2
├── resources/
│   ├── prompts/                     # Biblioteca de prompts
│   └── templates/                   # Templates listos para usar
├── context/                         # Propuestas y documentos internos
└── .claude/skills/                  # Skills de generación de contenido
```

---

## Convenciones

### Idioma y Encoding

- **Idioma:** Español latinoamericano
- **Encoding:** UTF-8 puro (tildes directas: á, é, í, ó, ú, ñ, ü)
- **Signos:** ¿?, ¡! (nunca omitir el signo de apertura)
- **Corrupción:** Si aparecen `�` o `\u00f3`, el archivo está corrupto — regenerar
- **Lenguaje público:** "asistente IA" (catálogo). Internamente: "agente" (README, labs, facilitator)

### Enlaces Externos (GitHub Pages / Kramdown)

```markdown
# Externos: SIEMPRE con {:target="_blank"}
[Claude](https://claude.ai/){:target="_blank"}

# Internos: NUNCA con target
[Clase 01](../class-01/)
[Sección](#seccion)
```

### Emojis

Estratégicos en headers para escaneo visual. No decorativos ni excesivos.

---

## Tono por Tipo de Archivo

| Archivo | Audiencia | Tono | Persona |
|---------|-----------|------|---------|
| `README.md` | Estudiante (pre-clase) | Profesional, inspirador | Segunda persona ("descubrirás") |
| `lab/README.md` | Estudiante (en clase) | Práctico, paso a paso | Segunda persona ("configura", "verifica") |
| `slides/README.md` | Facilitador (en clase) | Educativo, conversacional | Mixta |
| `facilitator/README.md` | Instructor (pre-clase) | Reflexivo, mentor-a-mentor | Narrativo estilo Medium |
| `infographic/index.html` | Estudiante (post-clase) | Visual, resumen rápido | Impersonal (conceptos) |

---

## Límites por Archivo

| Archivo | Límite | Notas |
|---------|--------|-------|
| `README.md` | ~150 líneas | Solo resumen y preparación |
| `lab/README.md` | ≤200 líneas | Laboratorio paso a paso |
| `slides/README.md` | ≤13 slides | Reveal.js markdown (separador `---`) |
| `facilitator/README.md` | <300 líneas | ~8 min lectura |
| `infographic/index.html` | 3-5 bloques | HTML autocontenido, 1080px ancho |

---

## Tipos de Lab

Determinar tipo según posición de la clase en el módulo:

```
Posición = ((clase - 1) % 4) + 1
Lab calificado = (Posición == 4)
```

| Tipo | Clases | Partes | Tiempo | Rúbrica |
|------|--------|--------|--------|---------|
| Regular | 1-3, 5-7 | 3 | ~60 min (en clase) | No |
| Calificado | 4, 8 | 5 (incluye Desafío) | ~90 min (50% clase + 50% post) | Sí |

---

## Sistema de Evaluación

Leer de `README.md`. Reglas derivadas:

- Solo la **última clase de cada módulo** tiene lab calificado (clases 4 y 8)
- Clase 8 es Demo Day (presentaciones de 5 min con demo en vivo)
- Tests diagnósticos: NO afectan calificación, son control interno
- Aprobación: puntaje mínimo 70/100, asistencia mínima 6/8 sesiones

---

## Scaffolding

> Variables de nivel para que los skills compartidos adapten su output.
> Los skills leen esta sección y ajustan gaps, checkpoints e instrucciones.
> Si esta sección no existe, usar defaults: `course_level=1`, `guided`, `Parte`, `visual`.

### Variables de Nivel

| Variable | Valor | Descripción |
|----------|-------|-------------|
| `course_level` | 1 | Complejidad general (1=intro, 2=intermedio, 3=avanzado) |
| `scaffolding_style` | guided | Estilo: `guided` / `descriptive` / `spec-based` |
| `part_naming` | Parte | Nombre de secciones del lab: `Parte` / `HU` |
| `checkpoint_style` | visual | Tipo de checkpoints: `visual` / `functional` / `sprint-based` |
| `instruction_style` | step-by-step | Redacción: `step-by-step` / `constrained-tasks` / `acceptance-criteria` |
| `gap_types` | comment-placeholders | Tipos de gap: `comment-placeholders` / `+blank-lines` / `+pseudocode,multiple-choice` |
| `class_duration` | 150 | Duración anunciada de la clase en minutos |
| `buffer` | 30 | Minutos reservados para imprevistos (preguntas, retrasos técnicos) |

### Tabla de Autonomía por Módulo

| Módulo | Código Completo | Gaps | Descripción |
|--------|-----------------|------|-------------|
| M1 | 90% | 10% | Instrucciones detalladas, el estudiante personaliza dentro de pasos claros |
| M2 | 85% | 15% | Más decisiones propias, el estudiante elige herramientas y configura agentes |

### Formato de Gaps por Nivel

**Nivel 1 (guided):** Gaps de personalización — el estudiante completa contenido propio dentro de flujos guiados.

```
Prompt: "Actúa como [<!-- Tu rol profesional -->] experto en [<!-- Tu área -->].
Tu tarea es [<!-- describe la tarea específica -->]."
```

### Checkpoints por Nivel

**visual** (Nivel 1): Describe lo que el estudiante debe VER en pantalla.
> ✅ **Checkpoint:** Tu Claude Project muestra el framework personalizado y responde usando tu contexto profesional.

### Densidad de Contenido

AI 101 es un curso **no-code para profesionales**. No se enseña programación.

- Los labs guían al estudiante por interfaces gráficas (Claude, Gemini, v0, Make, Vercel)
- Los "gaps" son decisiones de contenido (qué prompt escribir, qué configurar), no código
- Cuando hay código (v0, webhooks), el estudiante lo obtiene generado por IA y lo configura — no lo escribe
- Herramientas máximas por clase: 2 nuevas (regla MAX_TWO_NEW_TOOLS)

---

## Pipeline de Generación de Contenido

### Flujo para un módulo nuevo

```
1. module-planner  →  MODULE-PLAN.md (requiere aprobación humana)
2. Para cada clase (secuencial):
   class-readme → class-lab → class-slides → class-facilitator → class-infographic
3. En última clase del módulo:
   module-test
4. evaluation-class (verificar cada clase)
5. lint-markdown (validar enlaces y formato)
```

### Flujo para actualizar módulo existente

```
1. module-updater (auditar)  →  Reporte de drift en conversación
2. Usuario aprueba plan      →  Total, parcial, o solo parches
3. module-updater (implementar) → Parches → Ediciones → Regeneraciones
4. lint-markdown (validar archivos modificados)
```

### Dependencias entre archivos

| Al generar... | Leer primero... |
|---------------|-----------------|
| `README.md` de clase | `README.md` del curso, `MODULE-PLAN.md`, clase anterior |
| `lab/README.md` | `README.md` de la clase, `slides/README.md` |
| `slides/README.md` | `README.md` de la clase, `lab/README.md` |
| `facilitator/README.md` | Todos los anteriores de la clase |
| `infographic/index.html` | `README.md` de la clase, `slides/README.md`, `lab/README.md`, `facilitator/README.md` |
| `test/` | READMEs y slides de las 4 clases del módulo |

### Regla de contexto

Nunca generar contenido sin leer los archivos de dependencia. Si un archivo de dependencia no existe, generarlo primero o pedir al usuario que lo proporcione.

---

## Modificar Contenido Existente

1. Actualizar PRIMERO `README.md` (syllabus) si el cambio afecta estructura
2. Los archivos de clase referencian al syllabus — no duplicar tablas
3. Ejecutar lint-markdown antes de considerar completo

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
