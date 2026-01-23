---
name: class-lab
description: Genera laboratorios prácticos para clases de AI 101. Usar cuando se pida crear lab, laboratorio, práctica guiada, o ejercicio de clase.
allowed-tools: Read, Glob, Grep, Write, Edit
---

# Generador de Laboratorios - AI 101

## Objetivo

Crear laboratorios prácticos donde los estudiantes construyen piezas de su portfolio de super-usuario IA. Cada lab produce un entregable concreto y verificable.

## Decisiones de Diseño

| Aspecto | Decisión |
|---------|----------|
| **Arquitectura** | Incremental - cada lab construye sobre el anterior |
| **Entregables** | Screenshots, prompts documentados, contenido, workflows |
| **Checkpoints** | Verificables visualmente (NO técnicos) |
| **Duración** | 60 min en clase |
| **Tono** | Práctico, paso a paso, empoderador |

---

## Proceso de Generación

### Paso 1: Identificar contexto

```
Clase X → Módulo = floor((X-1)/4) + 1
        → Posición = ((X-1) % 4) + 1
        → Es cierre de módulo = (Posición == 4)
```

### Paso 2: Leer recursos previos

```bash
# Clase actual
curriculum/class-{X}/README.md
curriculum/class-{X}/slides/README.md

# Clase anterior (para continuidad)
curriculum/class-{X-1}/lab/README.md

# Syllabus (contexto del módulo)
context/course_syllabus.md
```

### Paso 3: Generar archivo

- `curriculum/class-{X}/lab/README.md`

---

## Template: Lab Regular (Clases 1-3, 5-7)

```markdown
# Lab: [Título del Lab]

## Objetivo

[1-2 párrafos describiendo qué construirá el estudiante y por qué es útil]

---

## Tiempo Estimado

**60 minutos** (completable en clase)

---

## Antes de Empezar

Verifica que tengas:

| ✓ | Requisito | Cómo verificar |
|---|-----------|----------------|
| ☐ | [Cuenta/herramienta lista] | [Instrucción] |
| ☐ | [Elemento de clase anterior] | [Instrucción] |

> Si te falta algo, coordina con tu facilitador antes de continuar.

---

## Parte 1: [Título] (~20 min)

### 1.1 [Subtarea]

[Explicación breve de qué haremos]

**Pasos:**
1. [Paso concreto con ejemplo]
2. [Paso concreto]
3. [Paso concreto]

> **Tip:** [Consejo útil para esta parte]

### 1.2 [Subtarea]

[Explicación breve]

**Ejemplo:**
```
[Prompt o contenido de ejemplo]
```

**Tu turno:**
```
[Espacio para que el estudiante complete]
```

✅ **Checkpoint:** [Descripción de lo que debe estar listo - ej: "Tienes 2 prompts funcionando y documentados"]

---

## Parte 2: [Título] (~20 min)

### 2.1 [Subtarea]

[Contenido con espacios para completar]

### 2.2 [Subtarea]

[Contenido con espacios para completar]

**Tabla para completar:**

| Elemento | Tu respuesta |
|----------|--------------|
| [Campo 1] | |
| [Campo 2] | |

✅ **Checkpoint:** [Descripción del resultado esperado]

---

## Parte 3: [Título] (~20 min)

### 3.1 [Subtarea]

[Contenido con espacios para completar]

### 3.2 [Subtarea]

[Contenido con espacios para completar]

✅ **Checkpoint:** [Descripción del resultado esperado]

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué fue lo más útil que aprendiste hoy?**
2. **¿Cómo aplicarías esto en tu trabajo esta semana?**
3. **¿Qué pregunta te quedó sin responder?**

---

## Entregable

### Checklist

- [ ] [Requisito específico 1]
- [ ] [Requisito específico 2]
- [ ] [Requisito específico 3]
- [ ] Reflexión completada

### Formato de Entrega

📄 **[Tipo de entregable]** que incluya:
- [Elemento verificable 1]
- [Elemento verificable 2]
- Tu nombre visible

> Comparte el enlace/screenshot en [plataforma].

---

## Bonus (Opcional)

### Nivel 1: [Título]
[Extensión simple del lab]

### Nivel 2: [Título]
[Extensión intermedia que introduce concepto futuro]

### Nivel 3: [Título]
[Extensión avanzada - preview de próximas clases]
```

---

## Template: Lab de Cierre de Módulo (Clases 4 y 8)

```markdown
# Lab: [Título - Integrador del Módulo]

> **Cierre de Módulo** - Este lab integra todo lo aprendido en las últimas 4 clases.

## Objetivo

[2-3 párrafos describiendo:
- Qué construirá el estudiante
- Cómo integra conceptos anteriores
- Por qué es importante para su portfolio]

---

## Tiempo Estimado

**60 minutos** (completable en clase)

---

## Antes de Empezar

Este lab integra todo el Módulo X. Verifica que tengas:

| ✓ | Requisito | De la Clase |
|---|-----------|-------------|
| ☐ | [Elemento del lab X-3] | Clase X-3 |
| ☐ | [Elemento del lab X-2] | Clase X-2 |
| ☐ | [Elemento del lab X-1] | Clase X-1 |

> Si te falta algo, este es el momento de completarlo.

---

## Parte 1: [Título] (~20 min)

[Contenido que usa elementos de clases anteriores]

✅ **Checkpoint:** [Descripción]

---

## Parte 2: [Título] (~20 min)

[Contenido que integra múltiples herramientas/conceptos]

✅ **Checkpoint:** [Descripción]

---

## Parte 3: [Título] (~20 min)

[Contenido de aplicación práctica final]

✅ **Checkpoint:** [Descripción]

---

## Reflexión del Módulo

Responde en tu documento:

1. **¿Qué habilidad de este módulo te parece más valiosa para tu trabajo?**
2. **¿Qué cambiarías en tu forma de trabajar a partir de hoy?**
3. **¿Qué área te gustaría explorar más en el siguiente módulo?**

---

## Entregable del Módulo

### Checklist

- [ ] [Componente 1 del portfolio de módulo]
- [ ] [Componente 2 del portfolio de módulo]
- [ ] [Componente 3 del portfolio de módulo]
- [ ] Reflexión del módulo completada

### Formato de Entrega

📦 **Portfolio de Módulo X** que incluya:
- [Elemento específico 1]
- [Elemento específico 2]
- [Elemento específico 3]

> Fecha de entrega: [fecha]

---

## Bonus (Opcional)

### Nivel 1: [Título]
[Preview de concepto del siguiente módulo - nivel introductorio]

### Nivel 2: [Título]
[Preview de concepto del siguiente módulo - nivel intermedio]
```

---

## Reglas de Contenido

### Límites de Estructura

| Elemento | Lab Regular | Lab Cierre | Notas |
|----------|-------------|------------|-------|
| **Objetivo** | 1-2 párrafos | 2-3 párrafos | Claro y motivador |
| **Partes del lab** | 3 | 3 | ~20 min cada una |
| **Checkpoints** | 3 | 3 | Verificables visualmente |
| **Bonus** | 3 niveles | 2 niveles | Opcional |
| **Reflexión** | 3 preguntas | 3 preguntas | Siempre incluir |
| **Líneas máximo** | ~200 | ~200 | Conciso |

### Checkpoints Verificables

Los checkpoints describen lo que el estudiante DEBE TENER:

**Incorrecto (vago):**
> ✅ **Checkpoint:** Completaste la parte 1

**Correcto (verificable):**
> ✅ **Checkpoint:** Tienes 3 prompts documentados con sus resultados en tu documento

### Tipos de Entregables por Clase

| Clase | Entregable |
|-------|------------|
| 1 | Screenshot de resultado impresionante + reflexión |
| 2 | 3 prompts maestros documentados |
| 3 | Contenido profesional publicable |
| 4 | Research doc + asistente configurado |
| 5 | 1 flujo automatizado funcionando |
| 6 | Asistente personalizado documentado |
| 7 | Caso de éxito publicable |
| 8 | Presentación + plan de desarrollo |

---

## Herramientas por Módulo

| Módulo | Herramientas |
|--------|--------------|
| M1 | Claude, Gemini, Perplexity, Google Docs |
| M2 | Make/Zapier, Notion, Claude |

---

## Validación Final

### Lab Regular (clases 1-3, 5-7)

- [ ] Duración ~60 min (3 partes de ~20 min)
- [ ] Espacios para completar (no todo dado)
- [ ] Checkpoints son verificables visualmente
- [ ] 3 niveles de Bonus
- [ ] Reflexión incluida (3 preguntas)
- [ ] Checklist de entrega claro
- [ ] ≤ 200 líneas

### Lab de Cierre (clases 4, 8)

- [ ] Integra conceptos de las 3 clases anteriores
- [ ] Duración ~60 min
- [ ] Checkpoints verificables
- [ ] 2 niveles de Bonus con preview
- [ ] Reflexión del módulo (3 preguntas)
- [ ] Checklist de entrega del portfolio
- [ ] ≤ 200 líneas
