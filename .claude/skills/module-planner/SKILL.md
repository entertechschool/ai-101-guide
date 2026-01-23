---
name: module-planner
description: Planifica la arquitectura completa de un módulo (4 clases) de AI 101. Usar ANTES de crear clases individuales. Genera MODULE-PLAN.md para aprobación.
allowed-tools: Read, Glob, Grep, WebSearch, AskUserQuestion
---

# Planificador de Módulos - AI 101

## Objetivo

Diseñar la arquitectura completa de un módulo de 4 clases ANTES de crear los recursos individuales. Este skill genera un documento `MODULE-PLAN.md` que sirve como blueprint para los demás skills.

---

## Cuándo Usar Este Skill

| Escenario | Usar |
|-----------|------|
| Crear módulo nuevo desde cero | Sí |
| Ajustar módulo existente (reordenar, actualizar, expandir) | Sí |
| Crear una sola clase de un módulo ya planificado | No (usar skills individuales) |
| Evaluar calidad de clases existentes | No (usar `evaluation-class`) |

---

## Filosofía de Diseño

### Principio Central
**"Las competencias definen el destino; el portfolio es el vehículo"**

### Patrones Obligatorios para AI 101

1. **Portfolio Incremental**
   - Los 4 labs construyen piezas del MISMO portfolio
   - Cada clase añade UNA habilidad demostrable
   - El estudiante ve evolución concreta de sus capacidades

2. **Estructura de Módulos**

   **M1: Fundamentos + Primeros Superpoderes (Clases 1-4)**
   ```
   Clase 1: Mindset     → Qué puede y no puede la IA + setup
   Clase 2: Prompting   → Técnicas avanzadas de prompt
   Clase 3: Contenido   → Escribir con IA (emails, posts, reportes)
   Clase 4: Research    → Gemini + Perplexity para investigación
   ```

   **M2: Superpoderes Aplicados + Portfolio (Clases 5-8)**
   ```
   Clase 5: Automatización → Zapier/Make sin código
   Clase 6: Asistente      → Custom instructions + segundo cerebro
   Clase 7: Portfolio      → Caso de éxito + documentación
   Clase 8: Presentación   → Demo Day + plan de desarrollo
   ```

3. **Conexiones Explícitas**
   - Cada lab referencia qué se necesita de la clase anterior
   - "Bonus" anticipa el siguiente tema
   - La clase 4 y 8 integran conceptos del módulo

4. **Cierre de Módulo (Clases 4 y 8)**
   - Test diagnóstico de 8 preguntas (15 min)
   - No afecta calificación
   - Mide comprensión y satisfacción

---

## Proceso de Planificación

### Fase 1: Recopilar Contexto

```
1. Identificar número de módulo (M)
   - M1 = clases 1-4 (Fundamentos + Primeros Superpoderes)
   - M2 = clases 5-8 (Superpoderes Aplicados + Portfolio)

2. Leer contexto existente:
   - context/course_syllabus.md (fuente de verdad)
   - CLAUDE.md (convenciones del proyecto)
   - Si M > 1: módulo anterior (para continuidad)

3. Obtener del usuario:
   - Competencias objetivo (qué debe SABER HACER el estudiante)
   - Herramientas principales
   - Conexión con módulo anterior (si aplica)
```

### Fase 2: Diseñar Arquitectura

```
1. Mapear competencias a clases
   - Una competencia principal por clase
   - Verificar que sean medibles y verificables

2. Diseñar progresión del portfolio
   - Qué tiene el portfolio al final de cada clase
   - Cómo cada pieza se construye sobre la anterior

3. Definir checkpoints por lab
   - 3 checkpoints para labs regulares (clases 1-3, 5-7)
   - El entregable debe ser verificable (screenshot, documento, prompt)

4. Identificar conexiones
   - Pre-requisitos del módulo anterior
   - Semillas para el módulo siguiente
```

### Fase 3: Generar MODULE-PLAN.md

Crear documento en: `curriculum/module-{M}/MODULE-PLAN.md`

---

## Template: MODULE-PLAN.md

```markdown
# Plan del Módulo {N}: {Título}

> Este documento define la arquitectura del módulo. Aprobar antes de crear clases.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | {N} |
| **Título** | {Título descriptivo} |
| **Tema Central** | {Descripción breve} |
| **Clases** | {Rango} |
| **Pre-requisitos** | {Qué necesita saber el estudiante} |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **{Competencia 1}** - {verbo de acción + objeto + contexto}
2. **{Competencia 2}** - {verbo de acción + objeto + contexto}
3. **{Competencia 3}** - {verbo de acción + objeto + contexto}
4. **{Competencia 4}** - {verbo de acción + objeto + contexto}

---

## Portfolio del Módulo

### Descripción
{2-3 párrafos describiendo:
- Qué construye el estudiante
- Por qué es relevante para su carrera
- Qué aprenderá en el proceso}

### Evolución por Clase

| Clase | Enfoque | Pieza del Portfolio al Finalizar |
|-------|---------|----------------------------------|
| {X} | {Tema} | {Descripción del entregable} |
| {X+1} | {Tema} | {Qué se añade} |
| {X+2} | {Tema} | {Qué se añade} |
| {X+3} | {Tema} | {Estado final del módulo} |

### Entregables del Módulo
{Lista de lo que entrega el estudiante al final del módulo}

---

## Arquitectura de Clases

### Clase {X}: {Título}

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | {UN solo concepto de IA} |
| **Objetivo del Lab** | {Qué construye/crea} |
| **Herramientas** | {Claude, Gemini, etc.} |
| **Entregable** | {Screenshot / documento / prompts} |

**Checkpoints del Lab:**
1. {Checkpoint verificable - describe QUÉ debe tener}
2. {Checkpoint 2}
3. {Checkpoint 3}

**Glosario de la Clase:**
| Término | Definición breve |
|---------|------------------|
| {Término 1} | {Definición} |

**Dependencias:**
- **Requiere:** {Nada / Conceptos del módulo anterior}
- **Habilita:** {Qué conceptos de la siguiente clase dependen de esto}

---

### Clase {X+3} (Cierre de Módulo): {Título}

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | {Integración + concepto nuevo} |
| **Objetivo del Lab** | Demostrar dominio del módulo completo |
| **Herramientas** | {Todas las del módulo} |
| **Entregable** | Portfolio de módulo completo |
| **Test Diagnóstico** | 8 preguntas (15 min) |

**Checkpoints del Lab:**
1. {Checkpoint 1}
2. {Checkpoint 2}
3. {Checkpoint 3}

---

## Checklist de Verificación

Antes de aprobar este plan, verificar:

- [ ] Las 4 competencias son medibles con verbos de acción
- [ ] Cada clase tiene UN concepto principal claro
- [ ] Los checkpoints son verificables (screenshot, documento)
- [ ] Las dependencias entre clases son explícitas
- [ ] La clase 4/8 integra conceptos de las 3 anteriores
- [ ] Hay conexión clara con módulos adyacentes
- [ ] El glosario cubre todos los términos nuevos
- [ ] context/course_syllabus.md está actualizado
```

---

## Herramientas por Módulo

| Módulo | Herramientas |
|--------|--------------|
| M1 | Claude, ChatGPT (referencia), Gemini, Perplexity |
| M2 | Make/Zapier, Notion, Claude (custom instructions) |

---

## Validación Final

Después de generar MODULE-PLAN.md, verificar que:

1. **Coherencia vertical:** Cada clase prepara para la siguiente
2. **Coherencia horizontal:** Las 4 clases forman una unidad temática
3. **Medibilidad:** Todos los checkpoints son verificables
4. **Completitud:** El plan tiene toda la info necesaria para crear clases
5. **Realismo:** Los tiempos y alcances son alcanzables en 60 min de lab
6. **Relevancia:** Los ejemplos conectan con trabajo real del estudiante

---

## Mantenimiento de Fuente de Verdad

> **IMPORTANTE:** Después de aprobar un MODULE-PLAN.md, actualizar:

1. **context/course_syllabus.md:**
   - Verificar que el contenido del módulo coincide
   - Actualizar si hay cambios

2. **CLAUDE.md:**
   - Actualizar checklist de progreso si cambió

El syllabus es la **única fuente de verdad** del contenido. Todos los skills leen de ahí.
