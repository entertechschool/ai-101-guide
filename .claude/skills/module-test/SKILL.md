---
name: module-test
description: Genera tests diagnósticos al cierre de módulo (clases 4 y 8). Usar cuando se pida crear test, quiz, evaluación diagnóstica, o checkpoint de módulo.
allowed-tools: Read, Glob, Grep, Write, Edit
---

# Generador de Tests Diagnósticos - AI 101

## Objetivo

Crear tests de verificación rápida (15 min) para evaluar comprensión al final de cada módulo. Los tests son **diagnósticos internos** - NO afectan la calificación del estudiante.

## Propósito del Test

- Control interno de avance del grupo
- Identificar temas que necesitan refuerzo
- Ajustar ritmo/contenido si es necesario
- Medir satisfacción de forma imperceptible (pregunta 8)

---

## Estructura de Archivos

```
curriculum/class-XX/test/
├── README.md        # Info para estudiante (qué esperar)
└── questions.md     # Preguntas con respuestas (copy-paste a Canvas/Forms)
```

**Ubicación:** Solo en clases de cierre de módulo (4 y 8)

---

## Proceso de Generación

### Paso 1: Identificar contexto

Determinar:
- Número de clase (4 u 8)
- Módulo correspondiente (M1 o M2)
- Clases que cubre el test (1-4 o 5-8)

### Paso 2: Leer contenido del módulo

```bash
# Leer READMEs de las clases del módulo
curriculum/class-{X-3}/README.md
curriculum/class-{X-2}/README.md
curriculum/class-{X-1}/README.md
curriculum/class-{X}/README.md

# Leer slides para conceptos clave
curriculum/class-{X-3}/slides/README.md
...
```

### Paso 3: Generar archivos

1. `test/README.md` - Info para estudiante
2. `test/questions.md` - 8 preguntas formato Canvas

---

## Template: README.md (estudiante)

```markdown
# Test Módulo [N]: [Título del Módulo]

**Duración:** 15 min | **Preguntas:** 8 | **Formato:** Opción múltiple

---

## ¿Qué evalúa?

Este test verifica tu comprensión de los conceptos de las Clases [X-3] a [X]:

- [Tema de clase X-3]
- [Tema de clase X-2]
- [Tema de clase X-1]
- [Tema de clase X]

---

## Instrucciones

1. Se realiza en [plataforma] durante la clase
2. Tienes 15 minutos
3. Individual

> **Nota:** Este test es diagnóstico - nos ayuda a identificar qué temas necesitan más práctica. **No afecta tu calificación del curso.**
```

---

## Template: questions.md (Canvas/Forms)

```markdown
# Test Módulo [N] - Questions

**8 preguntas diagnósticas**

---

## Preguntas 1-2 (Clase [X-3]: [Tema])

### Pregunta 1
[Pregunta sobre concepto fundamental de la clase X-3]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

### Pregunta 2
[Segunda pregunta de la clase X-3]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

---

## Preguntas 3-4 (Clase [X-2]: [Tema])

### Pregunta 3
[Pregunta sobre concepto de la clase X-2]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

### Pregunta 4
[Segunda pregunta de la clase X-2]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

---

## Preguntas 5-6 (Clase [X-1]: [Tema])

### Pregunta 5
[Pregunta sobre concepto de la clase X-1]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

### Pregunta 6
[Segunda pregunta de la clase X-1]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

---

## Pregunta 7 (Clase [X]: [Tema])

### Pregunta 7
[Pregunta de aplicación práctica de la clase de cierre]

- A) [Opción]
- B) [Opción]
- C) [Opción]
- D) [Opción]

> Respuesta: [Letra]

---

## Pregunta 8 (Autoevaluación)

### Pregunta 8
Después de completar este módulo, ¿cómo describirías tu nivel de confianza
para [APLICACIÓN PRINCIPAL DEL MÓDULO]?

- A) Muy seguro/a - podría hacerlo sin ayuda
- B) Bastante seguro/a - con algo de referencia
- C) Algo inseguro/a - necesitaría bastante guía
- D) Muy inseguro/a - no sabría por dónde empezar

> Sin respuesta correcta - todas las opciones son válidas para diagnóstico
```

**Nota:** La Pregunta 8 mide satisfacción de forma imperceptible. No tiene respuesta correcta.

---

## Reglas de Contenido

### Distribución de Preguntas (7 técnicas + 1 autoevaluación)

| Pregunta | Clase | Tipo |
|----------|-------|------|
| 1-2 | Clase X-3 | Conceptos iniciales |
| 3-4 | Clase X-2 | Desarrollo del tema |
| 5-6 | Clase X-1 | Profundización |
| 7 | Clase X | Aplicación práctica |
| 8 | — | Autoevaluación (satisfacción oculta) |

### Tipos de Preguntas Sugeridas para AI 101

**Conceptuales:**
- ¿Qué es un prompt?
- ¿Cuál es la diferencia entre editar y generar contenido con IA?

**Aplicación:**
- ¿Cuál de estos prompts daría mejor resultado para [tarea]?
- ¿Qué herramienta usarías para [caso de uso]?

**Análisis:**
- ¿Por qué es importante dar contexto a la IA?
- ¿Cuál es el riesgo de confiar ciegamente en respuestas de IA?

### Formato de Opciones

- 4 opciones (A, B, C, D)
- Solo UNA respuesta correcta
- Distractores plausibles pero claramente incorrectos
- Evitar "Todas las anteriores" o "Ninguna de las anteriores"

---

## Temas por Módulo

### Módulo 1 (Test en Clase 4)
- Clase 1: Mindset IA, qué puede/no puede, setup
- Clase 2: Prompting (RICE, chain of thought, few-shot)
- Clase 3: Contenido (emails, reportes, editing vs generating)
- Clase 4: Research (Gemini Gems, Perplexity Spaces)

### Módulo 2 (Test en Clase 8)
- Clase 5: Automatización (triggers, actions, workflows)
- Clase 6: Asistente personalizado (custom instructions, memoria)
- Clase 7: Portfolio (caso de éxito, documentación)
- Clase 8: Presentación (storytelling, próximos pasos)

---

## Validación Final

- [ ] README.md es conciso (~20 líneas) y NO menciona "umbral de aprobación"
- [ ] README.md tiene nota de "NO afecta calificación"
- [ ] questions.md tiene exactamente 8 preguntas (7 técnicas + 1 autoevaluación)
- [ ] Preguntas 1-7: 4 opciones con respuesta marcada `> Respuesta: X`
- [ ] Pregunta 8: autoevaluación sin respuesta correcta
- [ ] Distribución: 2+2+2 (clases 1-3) + 1 (clase 4) + 1 (autoevaluación)
- [ ] Formato compatible con Canvas/Google Forms (copy-paste)
- [ ] Preguntas relevantes para AI 101 (no técnicas de programación)

---

## Notas Importantes

1. **Solo clases 4 y 8:** No generar tests para otras clases
2. **Timing:** El test se toma a mitad de la clase de cierre
3. **Propósito:** Diagnóstico interno, NO calificación
4. **Tono:** Las preguntas deben ser claras, no tramposas
5. **Relevancia:** Enfocarse en aplicación práctica, no memorización
