# AGENTS.md - AI 101 Guide

> Instrucciones para agentes AI que trabajan en este repositorio.
> Compatible con: Claude Code, GitHub Copilot, Cursor, Gemini CLI, Windsurf, Codex.

---

## Proyecto

Repositorio del curso **AI 101 — IA + Automatización No-Code para Profesionales** de EnterTechSchool. Contiene curriculum completo: READMEs, laboratorios, slides, guías de facilitador y tests diagnósticos. **8 sesiones de 60 min (8 horas)** para que profesionales construyan soluciones automatizadas que integran IA con herramientas no-code (Make + Gemini + Google Workspace), sin programar.

### Caso guía: el sistema de facturas

Las sesiones 2 a 6 construyen, pieza por pieza, un mismo sistema real: la **automatización de facturas** (subir factura a Drive → Make la detecta → Gemini extrae los datos → caen estructurados en un Sheet → reporte mensual con plantilla → envío por correo). **No hay protagonista con nombre**; el hilo conductor es el sistema mismo.

### Proyecto integrador (sesiones 7-8)

Durante las sesiones 1 a 6 el estudiante aprende cada pieza sobre el caso de facturas. En la **Sesión 7** elige un **caso real propio**, lo diagrama y construye una primera versión de su flujo con datos reales. En la **Sesión 8** lo presenta en Demo Day (caso → demo → resultados → aprendizajes).

---

## Fuente de Verdad

**`README.md` es la única fuente de verdad.** Contiene:

- Estructura del curso (2 módulos × 4 sesiones)
- Contenido clave y entregables por sesión
- Sistema de evaluación (pesos, aprobación, asistencia)
- Formato, modalidad y stack de herramientas

**Regla:** Leer SIEMPRE `README.md` antes de generar o modificar contenido. Nunca hardcodear información que ya está en el syllabus. Si hay conflicto entre un archivo de clase y `README.md`, el syllabus gana.

---

## Estructura del Repositorio

```
├── README.md                        # Syllabus (fuente de verdad)
├── AGENTS.md                        # Este archivo
├── CLAUDE.md                        # Configuración Claude Code
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
│   ├── prompts/                     # Biblioteca de prompts de referencia
│   └── templates/                   # Plantillas (Sheet, Slides, Blueprints Make)
├── fuente/
│   └── (sílabo v3 + PPTs)           # Material fuente del instructor (v3)
└── .claude/skills/                  # Skills de generación de contenido
```

---

## Convenciones

### Idioma y Encoding

- **Idioma:** Español latinoamericano
- **Encoding:** UTF-8 puro (tildes directas: á, é, í, ó, ú, ñ, ü)
- **Signos:** ¿?, ¡! (nunca omitir el signo de apertura)
- **Corrupción:** Si aparecen `�` o `\u00f3`, el archivo está corrupto — regenerar
- **Lenguaje público:** "asistente IA" o "sistema automatizado" (catálogo). Internamente: "flujo", "escenario de Make", "módulo Gemini"

### Enlaces Externos (GitHub Pages / Kramdown)

```markdown
# Externos: SIEMPRE con {:target="_blank"}
[Gemini](https://gemini.google.com/){:target="_blank"}

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
| `lab/README.md` | ≤200 líneas (regular) / ≤280 (calificado) | Laboratorio paso a paso |
| `slides/README.md` | ≤13 slides | Reveal.js markdown (separador `---`) |
| `facilitator/README.md` | <300 líneas | ~8 min lectura |
| `infographic/index.html` | 3-5 bloques | HTML autocontenido, 1080px ancho |

---

## Mini-proyecto por sesión

Cada sesión (60 min) incluye un **mini-proyecto en vivo** que produce un entregable concreto. No hay labs calificados aparte ni entregables post-clase.

| Tipo | Sesiones | Tiempo del mini-proyecto |
|------|----------|--------------------------|
| Estándar | 1-6 | ~25 min (dentro de la sesión de 60 min) |
| Extendido | 7-8 | ~55 min (proyecto integrador y Demo Day) |

> **Nota sobre la sesión 8:** es Demo Day — presentaciones en vivo de 5 min con estructura caso → demo → resultados → Q&A. Sin cálculo de ROI ni plan 30 días ni rúbrica de pares (no están en la fuente v3).

---

## Sistema de Evaluación

Leer de `README.md`. Reglas derivadas:

- **Práctica en clase calificada 0/100** por sesión (hizo / no hizo el mini-proyecto)
- **No hay entregables post-clase**
- Proyecto integrador (S7) + Demo Day (S8) son el cierre evaluativo
- Tests diagnósticos: NO afectan calificación, son control interno
- Se valora asistencia a las 8 sesiones y participación en la Apertura y el Cierre

---

## Scaffolding

> Variables de nivel para que los skills compartidos adapten su output.
> Los skills leen esta sección y ajustan gaps, checkpoints e instrucciones.
> Si esta sección no existe, usar defaults: `course_level=1`, `guided`, `Actividad`, `visual`.

### Variables de Nivel

| Variable | Valor | Descripción |
|----------|-------|-------------|
| `course_level` | 1 | Complejidad general (1=intro, 2=intermedio, 3=avanzado) |
| `scaffolding_style` | guided | Estilo: `guided` / `descriptive` / `spec-based` |
| `part_naming` | Paso | Nombre de secciones del mini-proyecto (pasos numerados 1, 2, 3...) |
| `checkpoint_style` | visual | Tipo de checkpoints: `visual` / `functional` / `documental` |
| `instruction_style` | step-by-step | Redacción: `step-by-step` / `constrained-tasks` / `acceptance-criteria` |
| `gap_types` | comment-placeholders | Tipos de gap: `comment-placeholders` / `+blank-lines` |
| `class_duration` | 60 | Duración de la sesión en minutos (60 min) |
| `buffer` | 5 | Cierre / margen al final de la sesión |
| `lab_duration_regular` | 25 | Minutos de mini-proyecto en sesiones 1-6 |
| `lab_duration_graded` | 55 | Mini-proyecto extendido (S7 integrador, S8 Demo Day) |
| `has_reflection` | true | Incluir sección de reflexión |
| `reflection_name` | Reflexión | Nombre de la sección |
| `achievements_name` | Logros Adicionales | Nombre de la sección opcional |
| `primary_deliverable` | Screenshot | Tipo de entregable principal |
| `has_demo_day` | true | Clase 8 es Demo Day |
| `demo_day_class` | 8 | Clase donde ocurre Demo Day |

### Tabla de Autonomía por Módulo

| Módulo | Contenido Guiado | Gaps | Descripción |
|--------|------------------|------|-------------|
| M1 (S1-4) | 90% | 10% | Instrucciones detalladas; el estudiante construye el caso de facturas dentro de pasos claros (prompts propios, datos de muestra) |
| M2 (S5-8) | 80% | 20% | El estudiante toma más decisiones (su caso real, su plantilla, su flujo) — proyecto integrador propio en S7 |

### Formato de Gaps por Nivel

**Nivel 1 (guided):** Gaps de personalización — el estudiante completa contenido propio dentro de flujos guiados.

```
Prompt: "Eres [<!-- Tu rol profesional -->] y trabajas en [<!-- Tu industria -->].
Me ayudarás a automatizar [<!-- tu reporte -->]."
```

### Checkpoints por Nivel

**visual** (Nivel 1): Describe lo que el estudiante debe VER en pantalla.
> ✅ **Checkpoint:** Tu escenario de Make muestra el módulo de Drive en verde y, al correr "Run once", aparece una fila nueva en tu Sheet.

### Densidad de Contenido

AI 101 es un curso **no-code para profesionales**. No se enseña programación.

- Los labs guían al estudiante por interfaces gráficas (Gemini, Make, Google Cloud, Google Sheets/Docs/Slides, Gmail, Google AI Studio)
- Los "gaps" son decisiones de contenido (qué prompt escribir, qué datos cargar, qué marcadores nombrar), no código
- Cuando hay "código" (JSON en prompts de Gemini API, nombres de campos en Make), el estudiante lo copia/adapta — no lo escribe desde cero
- Herramientas máximas por clase: **2 nuevas** (regla `MAX_TWO_NEW_TOOLS`)

### Herramientas nuevas por sesión

| Clase | Herramienta nueva | Ya conocida |
|-------|-------------------|-------------|
| 1 | Gemini (chat) | — |
| 2 | Make, Google Cloud (OAuth) | Gemini |
| 3 | Gemini API (Google AI Studio) | Make |
| 4 | Parse JSON + Data Structure, Gmail en Make | Make, Gemini |
| 5 | Google Slides/Docs (plantillas) | Make, Sheets |
| 6 | Filtros, routers, error handler | Todo el stack |
| 7 | (ninguna nueva) | Todo el stack |
| 8 | (ninguna nueva) | Todo el stack |

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

### Material fuente del instructor

El curso v3 se construye a partir del material del instructor en `fuente/`:

| Archivo | Contenido |
|---------|-----------|
| `silabo-ai-v3.docx` | Sílabo oficial v3 (fuente última) |
| `silabo-8sesiones-v3.xlsx` | Malla de las 8 sesiones (capacidad, objetivo MINEDU, fundamentos, mini-proyecto) |
| `sesion0N-*.pptx` | Presentación por sesión — su contenido se refleja casi tal cual en `slides/` |

> **Numeración directa:** sesión 1..8 = class-01..class-08.
> **Atención:** `dev/nuevo_silabus_walter/` es la fuente **v2 anterior** (ya usada en una actualización previa). **No usar para v3.**

### Regla de contexto

Nunca generar contenido sin leer los archivos de dependencia. Si un archivo de dependencia no existe, generarlo primero o pedir al usuario que lo proporcione.

---

## Modificar Contenido Existente

1. Actualizar PRIMERO `README.md` (syllabus) si el cambio afecta estructura
2. Los archivos de clase referencian al syllabus — no duplicar tablas
3. Ejecutar `lint-markdown` antes de considerar completo

---

## Principios Pedagógicos

Al crear contenido de clase, aplicar estos 9 principios:

1. **MOTIVATION_FIRST** — "Por qué" y valor práctico ANTES de cualquier técnica. Demo de impacto.
2. **ONE_CONCEPT_PER_CLASS** — UN concepto principal. No mezclar temas.
3. **REAL_WORK_ONLY** — Tareas reales del estudiante (caso de facturas en S1-6, su propio caso en S7-8), nunca ficticias. Entregable USABLE.
4. **VERIFIABLE_DELIVERABLE** — Screenshot, documento, Sheet, Slides, flujo funcionando. "Entendí" NO es entregable.
5. **EXPLICIT_DEPENDENCIES** — Declarar qué requiere de clases anteriores y qué habilita.
6. **MAX_TWO_NEW_TOOLS** — Máximo 2 herramientas nuevas por clase. 3+ = PROHIBIDO.
7. **PORTFOLIO_BY_DEFAULT** — Cada entregable ES pieza del sistema final. Sin tarea separada.
8. **ANTI_HYPE_ALWAYS** — Al menos 1 momento de limitaciones/errores por clase.
9. **CUMULATIVE_ARTIFACTS** — Cada sesión produce un artefacto que el estudiante reusa en la siguiente. El sistema de facturas (escenario de Make + Sheet + plantilla) es el artefacto vivo que crece sesión a sesión.
