---
name: class-slides
description: Genera slides reveal.js para clases de AI 101. Usar cuando se pida crear slides, presentación, o diapositivas para una clase.
allowed-tools: Read, Glob, Grep, Write, Edit
---

# Generador de Slides de Clase - AI 101

## Objetivo

Crear slides optimizados para facilitar la clase. No son material de estudio, son herramientas para el facilitador y puntos de sincronización con los estudiantes.

## Filosofía: Slides que Facilitan, No que Enseñan

Cada slide tiene un propósito específico:
- **TRANSICIÓN**: Conectar clases (entrada/salida)
- **DEMO**: Mostrar ejemplo en vivo
- **CHECKPOINT**: Sincronizar progreso del grupo
- **REFLEXIÓN**: Consolidar conceptos clave
- **PRÁCTICA**: Guiar ejercicio hands-on

## Proceso

1. **Leer contexto**:
   - `curriculum/class-{X}/README.md` (tema, objetivos)
   - `curriculum/class-{X}/lab/README.md` (partes para checkpoints)
   - `curriculum/class-{X-1}/README.md` (para transición de entrada)
   - `curriculum/class-{X+1}/README.md` (para preview de salida)
   - `README.md` (contexto general)

2. **Generar archivo**: `curriculum/class-{X}/slides/README.md`

## Estructura Fija (11-13 slides máximo)

```markdown
<!-- .slide: data-background="#0A192F" -->
# Clase XX: [Título]
## [Subtítulo descriptivo]

---

## Transición: [Clase X-1] → [Clase X]

### La clase pasada:
- Lo que ya saben/hicieron

### Hoy:
- Lo nuevo que aprenderán

> "Frase de transición memorable"

---

## ¿Por Qué Esto Importa?

### El problema:
[Dato o estadística relevante]

### La oportunidad:
[Cómo la IA resuelve esto]

> **Realidad:** [Anti-hype - qué SÍ y qué NO puede hacer]

---

## 🎯 Pregunta Detonadora

### [Pregunta desafiante con 4 opciones]

**A)** [Opción plausible pero incorrecta]

**B)** [Opción correcta]

**C)** [Opción plausible pero incorrecta]

**D)** [Opción plausible pero incorrecta]

> 🕐 30 segundos para pensar → levanten la mano

---

## Demo: [Nombre de la Demo]

### Antes (sin IA):
[Descripción del proceso tradicional]

### Después (con IA):
[Descripción del proceso mejorado]

> 🎬 **Demo en vivo** - [Descripción de lo que mostrará el facilitador]

---

## Concepto Clave: [Nombre]

### Definición:
[Explicación simple]

### Ejemplo:
[Ejemplo práctico]

### Anti-patrón:
[Error común a evitar]

---

## Lab Time

### Objetivo:
[Qué van a construir]

### Tiempo: 60 min

**Partes:**
1. [Parte 1] (~20 min)
2. [Parte 2] (~20 min)
3. [Parte 3] (~20 min)

> 💡 Tip: [Consejo para empezar]

---

## Checkpoint: Parte 1

### Verifica:
- [ ] [Elemento que debe estar listo]
- [ ] [Elemento que debe estar listo]

**Preguntas:**
- ¿Todos tienen [X]?
- ¿Alguien encontró algo interesante?

---

## Checkpoint: Parte 2

### Verifica:
- [ ] [Elemento que debe estar listo]
- [ ] [Elemento que debe estar listo]

---

## Checkpoint: Parte 3

### Verifica:
- [ ] [Elemento que debe estar listo]
- [ ] [Elemento que debe estar listo]

---

## Reflexión

### Hoy aprendiste:
- [Concepto 1]
- [Concepto 2]
- [Concepto 3]

### Pregunta para pensar:
[Pregunta reflexiva sobre aplicación]

---

## Preview: Clase [X+1]

### Hoy lograste:
- [Logro 1]
- [Logro 2]

### La próxima clase:
- [Preview de lo que viene]

> **Tarea:** [Descripción de tarea asíncrona]

---

## Entrega

- [Requisito 1]
- [Requisito 2]
- Enlace compartido en [plataforma]

### Próxima clase: [Título]
```

## Notas de Estilo

- **Formato**: Reveal.js markdown (separador `---`)
- **Fondo**: `data-background="#0A192F"` solo en portada
- **Código**: Solo prompts de ejemplo, nunca código de programación
- **Tablas**: Para comparaciones (antes/después, con IA/sin IA)
- **Emojis**: Moderados, solo para escaneo visual
- **Preguntas**: Abiertas, que generen discusión sobre aplicación práctica

## Tipos de Slides por Propósito

| Tipo | Icono | Propósito | Cuándo usar |
|------|-------|-----------|-------------|
| Portada | — | Identificar clase | Siempre primero |
| Transición | — | Conectar con clase anterior | Inicio |
| Por Qué | — | Motivar con datos reales | Después de transición |
| **Pregunta Detonadora** | 🎯 | **Kahoot-style, 4 opciones, genera debate** | **Después de "Por Qué", antes de Demo** |
| Demo | 🎬 | Mostrar ejemplo en vivo | Después de pregunta |
| Concepto | — | Explicar idea clave | Entre demos |
| Lab Time | — | Iniciar trabajo práctico | Centro de clase |
| Checkpoint | — | Sincronizar progreso | Después de cada parte |
| Reflexión | — | Consolidar aprendizaje | Antes del cierre |
| Preview | — | Anticipar próxima clase | Casi al final |
| Entrega | — | Recordar requisitos | Siempre último |

## Contenido Específico de AI 101

### Módulo 1 (Clases 1-4): Fundamentos
- Demos: Prompts básicos vs avanzados, before/after de contenido
- Reflexiones: Qué puede/no puede la IA, cuándo supervisar
- Conceptos: Prompting, context window, hallucinations, temperature

### Módulo 2 (Clases 5-8): Superpoderes Aplicados
- Demos: Automatizaciones, asistentes personalizados
- Reflexiones: ROI de automatización, cuándo vale la pena
- Conceptos: Workflows, triggers, custom instructions, memoria

## Meta

- **Líneas**: ~150 máximo
- **Slides**: 11-13 (no más)
- **Tiempo por slide**: ~2-3 min promedio
- **Checkpoints**: Uno por cada parte del lab

## Validación

- [ ] ≤ 13 slides
- [ ] Tiene transición de entrada (clase anterior)
- [ ] Tiene transición de salida (próxima clase)
- [ ] **Tiene Pregunta Detonadora (4 opciones, estilo Kahoot)**
- [ ] Al menos 1 demo en vivo
- [ ] Checkpoints para cada parte del lab
- [ ] Al menos 1 reflexión
- [ ] Slide de entrega con requisitos claros
- [ ] Anti-hype: menciona limitaciones de IA
- [ ] Ejemplos conectan con trabajo real

## Pregunta Detonadora: Guía de Diseño

La pregunta debe:
- Ser DESAFIANTE (no obvia)
- Tener 1 respuesta correcta y 3 distractores plausibles
- Conectar con el concepto principal de la clase
- Generar debate sobre "por qué las otras NO"

**Formato:**
```markdown
## 🎯 Pregunta Detonadora

### [Pregunta que rete sus suposiciones]

**A)** [Distractor plausible]
**B)** [Respuesta correcta]
**C)** [Distractor plausible]
**D)** [Distractor plausible]

> 🕐 30 segundos para pensar → levanten la mano
```

**IMPORTANTE:** La respuesta correcta y explicación de por qué las otras NO van en `facilitator/README.md`, NO en los slides.
