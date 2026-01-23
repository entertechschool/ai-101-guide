---
name: evaluation-class
description: Evalúa calidad y coherencia de una clase de AI 101 antes de publicar. Usar cuando se pida evaluar, revisar, QA, o diagnóstico de una clase.
allowed-tools: Read, Glob, Grep, Bash
---

# Evaluador de Clases - AI 101

## Objetivo

Verificar que una clase está lista para publicar, evaluando:
1. **Calidad individual** de cada recurso
2. **Coherencia horizontal** con clases adyacentes
3. **Coherencia vertical** con el módulo

## Proceso de Evaluación

### Paso 1: Identificar la clase

Extraer número de clase (X) del prompt del usuario.

### Paso 2: Determinar contexto

```
Módulo = floor((X - 1) / 4) + 1
Posición en módulo = ((X - 1) % 4) + 1
Es cierre de módulo = Posición == 4
```

### Paso 3: Leer recursos

```bash
# Clase actual
curriculum/class-{X}/README.md
curriculum/class-{X}/lab/README.md
curriculum/class-{X}/facilitator/README.md
curriculum/class-{X}/slides/README.md
curriculum/class-{X}/test/README.md         # Solo clases 4 y 8
curriculum/class-{X}/test/questions.md      # Solo clases 4 y 8

# Clases adyacentes (si existen)
curriculum/class-{X-1}/README.md
curriculum/class-{X+1}/README.md

# Contexto del módulo
context/course_syllabus.md
```

### Paso 4: Aplicar checklist

## Checklist de Evaluación

### 1. Recursos Individuales

#### README.md
| Criterio | Verificar |
|----------|-----------|
| Estructura | Tiene Resumen, "Por qué te sirve", Objetivos, Glosario |
| Longitud | ≤ 150 líneas |
| Objetivos | 3-4 items claros y medibles |
| Glosario | 4-6 términos de IA |
| Preparación | Incluye reflexión previa y herramientas necesarias |
| Tono | Segunda persona, motivacional, anti-hype |

#### lab/README.md
| Criterio | Verificar |
|----------|-----------|
| Longitud | ≤ 200 líneas |
| Partes | 3 partes de ~20 min cada una |
| Checkpoints | Verificables (screenshots, documentos) |
| Continuidad | Referencia a clase anterior (excepto clase 1, 5) |
| Reflexión | Incluye sección de reflexión (3 preguntas) |
| Entrega | Instrucciones claras de entregable |
| Bonus | 3 niveles (regular) o 2 niveles (cierre) |

#### facilitator/README.md
| Criterio | Verificar |
|----------|-----------|
| Longitud | < 250 líneas (~8 min lectura) |
| Conceptos clave | 3-5 definiciones |
| Analogías | 3-4 útiles para IA |
| Script de demo | Con plan B |
| Errores comunes | Tabla con 4-6 |
| Checkpoints | Tabla con tiempos (~150 min total) |
| Tips facilitación | Para situaciones comunes |

#### slides/README.md
| Criterio | Verificar |
|----------|-----------|
| Cantidad | ≤ 12 slides |
| Formato | Reveal.js markdown válido |
| Transiciones | Tiene entrada y salida |
| Demo | Al menos 1 demo en vivo |
| Checkpoints | Uno por parte del lab |
| Reflexión | 1-2 conceptos clave |

#### test/ (solo clases 4 y 8)
| Criterio | Verificar |
|----------|-----------|
| README.md | Conciso, menciona "no afecta calificación" |
| questions.md | 8 preguntas (7 técnicas + 1 autoevaluación) |
| Distribución | 2+2+2+1+1 por clase |
| Formato | Compatible con Canvas/Forms |

### 2. Coherencia Horizontal (X-1 → X → X+1)

| Aspecto | Verificar |
|---------|-----------|
| Conexión hacia atrás | README menciona clase anterior |
| | Slides tienen transición de entrada |
| | Lab usa conceptos de X-1 |
| Conexión hacia adelante | Facilitador planta semilla para X+1 |
| | Slides tienen preview |
| | Bonus anticipa siguiente tema |
| Curva de dificultad | Complejidad incrementa gradualmente |
| | No hay saltos conceptuales bruscos |

### 3. Coherencia Vertical (Módulo)

| Aspecto | Verificar |
|---------|-----------|
| Portfolio | Lab contribuye al portfolio del módulo |
| Preparación cierre | Si X es clase 1-3: prepara para clase 4 |
| | Si X es clase 5-7: prepara para clase 8 |
| Cierre de módulo | Si es clase 4 u 8: |
| | - Lab integra conceptos de las 3 anteriores |
| | - Incluye test diagnóstico |
| Adherencia syllabus | Tema coincide con course_syllabus.md |

## Formato de Output

```markdown
## Evaluación Clase X: [Título]

**Módulo:** M{N} | **Posición:** {P} de 4

---

### Puntuación: X/10

---

### Recursos Individuales

| Recurso | Estado | Observación |
|---------|--------|-------------|
| README.md | ✅/⚠️/❌ | [Detalle] |
| lab/README.md | ✅/⚠️/❌ | [Detalle] |
| facilitator/README.md | ✅/⚠️/❌ | [Detalle] |
| slides/README.md | ✅/⚠️/❌ | [Detalle] |
| test/ | ✅/⚠️/❌/N/A | [Detalle] |

---

### Coherencia Horizontal

| Conexión | Estado | Observación |
|----------|--------|-------------|
| ← Clase X-1 | ✅/⚠️/❌ | [Detalle] |
| → Clase X+1 | ✅/⚠️/❌ | [Detalle] |
| Curva dificultad | ✅/⚠️/❌ | [Detalle] |

---

### Coherencia Vertical

| Aspecto | Estado | Observación |
|---------|--------|-------------|
| Portfolio | ✅/⚠️/❌ | [Detalle] |
| Prep. cierre | ✅/⚠️/❌ | [Detalle] |
| Syllabus | ✅/⚠️/❌ | [Detalle] |

---

### Fortalezas
- [Punto fuerte 1]
- [Punto fuerte 2]

### Observaciones Menores
- [Mejora sugerida 1]
- [Mejora sugerida 2]

### Problemas Críticos
- [Problema que bloquea publicación]

---

### Recomendación Final

[ ] **Lista para publicar**
[ ] **Requiere ajustes menores** (listar)
[ ] **Requiere revisión mayor** (listar)
```

## Escala de Puntuación

| Puntos | Significado |
|--------|-------------|
| 10 | Perfecta, publicar sin cambios |
| 9 | Excelente, detalles mínimos opcionales |
| 8 | Muy buena, 1-2 ajustes menores |
| 7 | Buena, algunos ajustes recomendados |
| 6 | Aceptable, necesita mejoras |
| < 6 | No lista, requiere trabajo significativo |

## Criterios de Bloqueo

La clase NO está lista si:
- Falta README.md, lab/README.md, facilitator/README.md, o slides/README.md
- Clases 4 u 8 sin carpeta test/
- Tiempos del facilitator no suman ~150 min
- No hay conexión clara con clase anterior
- Facilitador tiene contenido de otra clase (error de copy-paste)
- Entregable del lab no es verificable
- Checkpoints del lab son vagos ("completaste la parte")
- Falta anti-hype (no menciona limitaciones de IA)

## Recursos por Tipo de Clase

### Clases Regulares (1-3, 5-7)
- README.md ✓
- lab/README.md ✓
- facilitator/README.md ✓
- slides/README.md ✓
- test/ ✗ (no aplica)

### Clases de Cierre (4, 8)
- README.md ✓
- lab/README.md ✓
- facilitator/README.md ✓
- slides/README.md ✓
- test/ ✓ (obligatorio)
