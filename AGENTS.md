# AGENTS.md - AI 101 Guide

> Instrucciones para agentes AI que trabajan en este repositorio.
> Compatible con: Claude Code, GitHub Copilot, Cursor, Gemini CLI, Windsurf, Codex.

---

## Proyecto

Repositorio del curso **AI 101 — IA estratégica para Profesionales** de EnterTechSchool. Contiene curriculum completo: READMEs, laboratorios, slides, guías de facilitador y tests diagnósticos. **8 sesiones en 4 semanas** para que profesionales construyan un sistema automatizado de recolección de datos y generación de reportes ejecutivos usando herramientas 100% gratuitas.

### Caso guía: Roberto

Todo el curso gira alrededor de un caso único: **Roberto, gerente de una pequeña empresa con 3-4 vendedores**, que pierde horas cada viernes consolidando reportes manuales. El estudiante construye el sistema que resuelve el problema de Roberto, y en el Módulo 2 lo personaliza a su propio trabajo.

### Proyecto de instrucción (hilo conductor)

Cada estudiante define en la Sesión 1 un **proyecto de instrucción**: un reporte real de su trabajo que quiere automatizar. Ese proyecto acompaña las 8 sesiones — cada sesión produce un entregable que se integra al sistema final. Al cerrar la Sesión 8, el estudiante presenta su sistema funcionando en vivo y calcula el ROI en horas ahorradas.

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
│   └── templates/                   # Plantillas (Gem, Sheet, Slides, Blueprints Make)
├── dev/
│   └── nuevo_silabus_walter/        # Material fuente del instructor
└── .claude/skills/                  # Skills de generación de contenido
```

---

## Convenciones

### Idioma y Encoding

- **Idioma:** Español latinoamericano
- **Encoding:** UTF-8 puro (tildes directas: á, é, í, ó, ú, ñ, ü)
- **Signos:** ¿?, ¡! (nunca omitir el signo de apertura)
- **Corrupción:** Si aparecen `�` o `\u00f3`, el archivo está corrupto — regenerar
- **Lenguaje público:** "asistente IA" o "sistema automatizado" (catálogo). Internamente: "flujo", "escenario de Make", "Gem"

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

## Tipos de Lab

Determinar tipo según posición de la clase en el módulo:

```
Posición = ((clase - 1) % 4) + 1
Lab calificado = (Posición == 4)
```

| Tipo | Clases | Partes | Tiempo | Rúbrica |
|------|--------|--------|--------|---------|
| Regular | 1-3, 5-7 | 3 actividades | ~105 min (en clase) | No |
| Calificado | 4, 8 | 3 actividades + Desafío | ~90 min clase + post | Sí |

> **Nota sobre la clase 8:** es Demo Day (presentaciones en vivo de 5 min + cálculo de ROI + plan 30 días), con rúbrica de pares.

---

## Sistema de Evaluación

Leer de `README.md`. Reglas derivadas:

- Solo la **última clase de cada módulo** tiene lab calificado (clases 4 y 8)
- Clase 8 es **Demo Day** (presentaciones de 5 min con demo en vivo + ROI)
- Tests diagnósticos: NO afectan calificación, son control interno
- Aprobación: puntaje mínimo 70/100, asistencia mínima 6/8 sesiones

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
| `part_naming` | Actividad | Nombre de secciones del lab (el sílabo usa "Actividad 1/2/3") |
| `checkpoint_style` | visual | Tipo de checkpoints: `visual` / `functional` / `documental` |
| `instruction_style` | step-by-step | Redacción: `step-by-step` / `constrained-tasks` / `acceptance-criteria` |
| `gap_types` | comment-placeholders | Tipos de gap: `comment-placeholders` / `+blank-lines` |
| `class_duration` | 150 | Duración anunciada de la clase en minutos (2.5h) |
| `buffer` | 15 | Minutos reservados para imprevistos |
| `lab_duration_regular` | 105 | Minutos de lab en clase regular (3 actividades × ~35 min) |
| `lab_duration_graded` | 135 | Lab calificado (clase + post-clase) |
| `has_reflection` | true | Incluir sección de reflexión |
| `reflection_name` | Reflexión | Nombre de la sección |
| `achievements_name` | Logros Adicionales | Nombre de la sección opcional |
| `primary_deliverable` | Screenshot | Tipo de entregable principal |
| `has_demo_day` | true | Clase 8 es Demo Day |
| `demo_day_class` | 8 | Clase donde ocurre Demo Day |

### Tabla de Autonomía por Módulo

| Módulo | Contenido Guiado | Gaps | Descripción |
|--------|------------------|------|-------------|
| M1 | 90% | 10% | Instrucciones detalladas; el estudiante personaliza dentro de pasos claros (brief propio, parámetros del negocio, datos de muestra) |
| M2 | 80% | 20% | El estudiante toma más decisiones (prompts propios, diseño de marca, caso real) con acompañamiento 1 a 1 en C07 |

### Formato de Gaps por Nivel

**Nivel 1 (guided):** Gaps de personalización — el estudiante completa contenido propio dentro de flujos guiados.

```
Prompt: "Eres [<!-- Tu rol profesional -->] y trabajas en [<!-- Tu industria -->].
Me ayudarás a automatizar [<!-- tu reporte -->]."
```

### Checkpoints por Nivel

**visual** (Nivel 1): Describe lo que el estudiante debe VER en pantalla.
> ✅ **Checkpoint:** Tu Gem muestra el nombre "Asistente de mi proyecto" y responde mencionando los datos de tu brief.

### Densidad de Contenido

AI 101 es un curso **no-code para profesionales**. No se enseña programación.

- Los labs guían al estudiante por interfaces gráficas (Gemini, Gems, Google Sheets/Slides, Make, Gmail)
- Los "gaps" son decisiones de contenido (qué prompt escribir, qué datos cargar, qué marcadores nombrar), no código
- Cuando hay "código" (JSON en prompts de Gemini API, nombres de campos en Make), el estudiante lo copia/adapta — no lo escribe desde cero
- Herramientas máximas por clase: **2 nuevas** (regla `MAX_TWO_NEW_TOOLS`)

### Herramientas nuevas por sesión

| Clase | Herramienta nueva | Ya conocida |
|-------|-------------------|-------------|
| 1 | Gemini, Gems | — |
| 2 | Google Sheets (con Gemini) | Gemini |
| 3 | Google Slides (con Gemini) | Gemini, Sheets |
| 4 | Make, Gmail en Make | Sheets, Slides |
| 5 | Gemini API, HTTP/JSON en Make | Make, Gemini |
| 6 | (ninguna nueva) | Todo el stack |
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

El curso v2 se construye a partir del material de Walter en `dev/nuevo_silabus_walter/`:

| Archivo | Contenido |
|---------|-----------|
| `silabo-ai-profesionales-basev2.docx.md` | Sílabo académico oficial (fuente última) |
| `PPTs/sesion{N}/sesion-*.md` | Notas detalladas del instructor por sesión (teoría, actividades, tiempos, verificación) |
| `PPTs/sesion{N}/ppt-sesion{N}-*.pptx.txt` | Texto extraído del PPT correspondiente |

> **Nota de numeración:** los PPTs (y sus `.txt`) tienen la numeración oficial (Sesión 1..8 = clase-01..class-08). Las notas `.md` de las sesiones 6, 7 y 8 tienen desfase heredado (dicen "Sesión 7", "8" y "9" internamente) pero corresponden a class-06, class-07 y class-08 respectivamente. Confiar en los PPTs para numeración.

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
3. **REAL_WORK_ONLY** — Tareas reales del estudiante (proyecto de instrucción), nunca ficticias. Entregable USABLE.
4. **VERIFIABLE_DELIVERABLE** — Screenshot, documento, Sheet, Slides, flujo funcionando. "Entendí" NO es entregable.
5. **EXPLICIT_DEPENDENCIES** — Declarar qué requiere de clases anteriores y qué habilita.
6. **MAX_TWO_NEW_TOOLS** — Máximo 2 herramientas nuevas por clase. 3+ = PROHIBIDO.
7. **PORTFOLIO_BY_DEFAULT** — Cada entregable ES pieza del sistema final. Sin tarea separada.
8. **ANTI_HYPE_ALWAYS** — Al menos 1 momento de limitaciones/errores por clase.
9. **CUMULATIVE_ARTIFACTS** — Cada sesión produce un artefacto que el estudiante reusa en la siguiente. La tabla de parámetros es el documento vivo del curso.
