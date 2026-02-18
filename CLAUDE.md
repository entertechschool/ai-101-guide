# CLAUDE.md - AI 101 Guide

## Referencia Principal
- **Syllabus (fuente de verdad):** [README.md](README.md)
- **Propuesta comercial:** [context/propuesta_02.md](context/propuesta_02.md)
- **Estructura:** 2 módulos (8 clases en 4 semanas)
- **Formato:** 3h síncronas + 2h asíncronas por clase = 40h total

---

## Checklist de Progreso

### M1: Fundamentos + Primeros Superpoderes (Clases 1-4)
- [x] **Clase 1:** El Nuevo Juego
- [x] **Clase 2:** El Arte del Prompt
- [x] **Clase 3:** Tu Socio Pensante
- [x] **Clase 4:** Proyecto Integrador M1

### M2: Superpoderes Aplicados + Portfolio (Clases 5-8)
- [ ] **Clase 5:** Tu Primer Agente IA
- [ ] **Clase 6:** Tu Agente Inteligente
- [ ] **Clase 7:** Mi Agente Real
- [ ] **Clase 8:** Demo Day + El Futuro

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

## Tiempos de Clase

| Audiencia | Tiempo | Notas |
|-----------|--------|-------|
| **Estudiante** | 180 min (3h) | Lo que se comunica públicamente |
| **Facilitador** | 150 min | Tiempo real de instrucción |
| **Lab** | 60 min | Incluido en los 150 min |

- El README del estudiante NO debe incluir tiempos detallados por fase
- La guía del facilitador SÍ incluye checkpoints con tiempos (~150 min)
- La diferencia de 30 min es buffer para breaks, troubleshooting, etc.

---

## Estructura de Archivos

### README.md (raíz de clase)
```markdown
> 📦 **Módulo X:** Clase Y de 4

# Título de la Clase

## Resumen (2-3 párrafos)
## ¿Por qué te sirve?
## ¿Qué haremos en clase? (sin tiempos)
## Objetivos de aprendizaje (3-4 items)
## Preparación para la clase
## Herramientas necesarias
```

### lab/README.md
```markdown
# Lab XX: Mi [Título]

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

## Principios Pedagógicos (OBLIGATORIO)

Al crear contenido de clase, aplicar estos 9 principios:

### 1. MOTIVATION_FIRST
Siempre presentar el "por qué" y el valor práctico ANTES de enseñar cualquier técnica. Iniciar con demo de impacto (antes/después).

### 2. ONE_CONCEPT_PER_CLASS
Cada clase tiene UN solo concepto principal. No mezclar temas aunque estén relacionados. El concepto principal define el nombre de la clase.

### 3. REAL_WORK_ONLY
Los ejercicios deben usar tareas reales del trabajo del estudiante, nunca casos ficticios. El entregable debe ser USABLE en su contexto laboral real.

### 4. VERIFIABLE_DELIVERABLE
Todo entregable debe ser verificable objetivamente: screenshot, documento, prompt guardado, link funcional. "Entendí el concepto" NO es entregable válido.

### 5. EXPLICIT_DEPENDENCIES
Cada clase debe declarar qué requiere de clases anteriores y qué habilita para clases siguientes. El lab de Clase N usa outputs de Clase N-1 cuando sea posible.

### 6. MAX_TWO_NEW_TOOLS
Introducir máximo 2 herramientas nuevas por clase. Si son 2, deben ser comparables o complementarias. 3+ herramientas nuevas = PROHIBIDO.

### 7. PORTFOLIO_BY_DEFAULT
Cada entregable de clase ES automáticamente una pieza del portfolio. No hay "tarea de armar portfolio" separada. Se construye clase a clase.

### 8. ANTI_HYPE_ALWAYS
Siempre mencionar limitaciones, errores comunes y qué NO puede hacer la IA. Cada clase incluye al menos 1 momento de "esto NO funciona así".

### 9. COMPETITIVE_COLLABORATION
Incluir al menos 1 "battle" por módulo donde todos resuelven el mismo reto y votan el mejor resultado. Mismo problema, trabajo individual, votación de pares, discusión post-battle.

### Checklist de Validación

```
[ ] MOTIVATION_FIRST: ¿Hay demo/ejemplo de impacto antes de la teoría?
[ ] ONE_CONCEPT_PER_CLASS: ¿Puedo nombrar EL concepto en 3 palabras?
[ ] REAL_WORK_ONLY: ¿El ejercicio usa trabajo real del estudiante?
[ ] VERIFIABLE_DELIVERABLE: ¿Puedo verificar el entregable sin subjetividad?
[ ] EXPLICIT_DEPENDENCIES: ¿Está claro qué necesita y qué habilita?
[ ] MAX_TWO_NEW_TOOLS: ¿Son máximo 2 herramientas nuevas?
[ ] PORTFOLIO_BY_DEFAULT: ¿El entregable es mostrable como portfolio?
[ ] ANTI_HYPE_ALWAYS: ¿Hay al menos 1 momento de limitaciones/errores?
[ ] COMPETITIVE_COLLABORATION: ¿Hay battle en este módulo? (mínimo 1)
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
- **Títulos de Lab:** Primera persona ("Mi") para ownership del estudiante

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

**README.md es la única fuente de verdad para:**
- Contenido de cada clase
- Estructura de módulos
- Entregables y tareas
- Descripción del curso
- Tabla de contenidos con links a clases

**Al modificar contenido:**
1. Actualizar primero README.md
2. Los demás archivos referencian a README.md

---

## Herramientas del Curso

| Herramienta | Propósito | Clase |
|-------------|-----------|-------|
| **Claude** | Asistente principal, Projects, sistemas | 1-3 |
| **Gemini** | Deep Research, Gems personalizados | 4 |
| **Perplexity** | Research con fuentes verificables | 4 |
| **Make/n8n** | Agentes y automatización | 5 |
| **Google Sheets** | Logging de agente (en Make) | 6 |
| **GitHub** | Repositorio open-source, documentación de SystemPrompts | 7 |
| **LinkedIn** | Publicación de caso de éxito | 8 |

---

## Entregables por Clase

| Clase | Entregable |
|-------|------------|
| 1 | Screenshot resultado + reflexión |
| 2 | Evolución de prompt + reflexión crítica |
| 3 | Claude Project + framework personal |
| 4 | Proyecto integrador M1 (calificable) |
| 5 | 1 agente funcionando |
| 6 | Agente inteligente con Router + Sheets |
| 7 | Agente en Vercel + repo GitHub con SystemPrompts |
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

*Última actualización: 2026-01-31*

- Propuesta 02 aprobada: 8 clases en 4 semanas
- Nombre: "AI 101 - Desbloqueando el verdadero poder de la IA"
- Enfoque: Super-usuario de IA (no constructor)
- Duración: 40h total (24h sync + 16h async)
- Estructura de carpetas simplificada vs Code 301
- 8 skills de Claude Code creados para generación de contenido
- **M1 completado:** Clases 01-04 implementadas
  - Clases 01-02: Patrón "Tú → IA"
  - Clase 03: Patrón "IA ↔ Tú" (socio pensante)
  - Clase 04: Proyecto integrador calificable
