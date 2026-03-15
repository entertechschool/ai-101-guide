---
name: class-facilitator
description: Genera guías de facilitador para clases de AI 101. Usar cuando se pida crear guía de facilitador, guía del instructor, material para el profesor, o facilitator guide.
allowed-tools: Read, Glob, Grep, WebSearch, WebFetch, Write, Edit
---

# Generador de Guías de Facilitador - AI 101

## Objetivo

Crear guías de referencia rápida (lectura 5-10 min antes de clase) para instructores del bootcamp. El tono debe ser narrativo, mentor-a-mentor, con consejos prácticos.

## Proceso

1. **Leer el contenido de la clase**: README.md, lab/README.md, slides/README.md
2. **Investigar contexto**: Usar WebSearch para obtener datos actuales sobre IA
3. **Generar el archivo**: `curriculum/class-XX/facilitator/README.md`

## Estructura del Documento

```markdown
# Guía del Facilitador - Clase XX: [Título]

> Tiempo de lectura: X minutos | Prepárate antes de clase

---

## Conceptos Clave

- **[Concepto 1]**: Definición de 1 línea.
- **[Concepto 2]**: Definición de 1 línea.
- **[Concepto 3]**: Definición de 1 línea.

(3-5 conceptos máximo, solo lo esencial)

---

## Analogías Útiles

**[Concepto de IA] como [Analogía cotidiana]:**
Explicación de por qué funciona esta analogía. 2-3 líneas máximo.

(3-4 analogías listas para usar en clase)

---

## Contexto Actual

### [Tema]: [Título narrativo]

Contexto relevante sobre el estado actual de la IA:
- Qué está pasando en la industria
- Por qué es relevante para los estudiantes
- Cómo conecta con lo que veremos hoy

> **Para mencionar en clase:** "Dato o cita relevante"

**Fuentes:** [Link 1](url)

---

## Momentos Clave de la Clase

### Pregunta Detonadora

**Respuesta correcta:** [Letra] - [Opción]

**Por qué las otras NO:**
| Opción | Por qué NO |
|--------|-----------|
| A | [Explicación concisa de por qué es incorrecta] |
| C | [Explicación concisa de por qué es incorrecta] |
| D | [Explicación concisa de por qué es incorrecta] |

**Script post-votación:**
```
Facilitador: "¿Quién votó A? ¿Por qué?"
[Escuchar respuestas]
Facilitador: "Interesante. La respuesta es [X] porque [razón clave]."
Facilitador: "Las otras opciones fallan porque [resumen rápido]."
```

**Tip:** No revelar la respuesta inmediatamente. Dejar que debatan 1-2 minutos.

---

### Demo Principal

**Qué mostrar:**
[Descripción específica de la demo]

**Script sugerido:**
```
Facilitador: "Voy a mostrarles cómo [tarea] que normalmente toma [tiempo]..."
[Hacer la demo]
Facilitador: "¿Notaron cómo [punto clave]?"
```

**Si algo sale mal:**
[Plan B si la demo no funciona]

### Transición al Lab

**Momento crítico:**
La transición de la demo al lab es donde más estudiantes se pierden.

**Script sugerido:**
```
Facilitador: "Ahora ustedes van a hacer algo similar. Abran [herramienta]..."
Facilitador: "El primer paso es [paso específico]. Levanten la mano cuando tengan [checkpoint]."
```

---

## Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "La IA me da respuestas genéricas" | Prompts sin contexto | Mostrar diferencia con/sin contexto |
| "No sé qué preguntarle" | Falta de claridad en objetivo | Preguntar: "¿Qué quieres lograr?" |
| "Los resultados no son útiles" | Expectativas desalineadas | Recordar: IA como borrador, no producto final |

(4-6 errores típicos de estudiantes)

---

## Preguntas Frecuentes

### "¿Claude o ChatGPT?"
Respuesta: Ambos son útiles. Claude tiende a ser mejor para [X], ChatGPT para [Y]. Lo importante es dominar los principios que funcionan en ambos.

### "¿Esto va a reemplazar mi trabajo?"
Respuesta: La IA no reemplaza trabajos, reemplaza tareas. Tu trabajo será diferente, no inexistente. Los que dominan IA serán más valiosos, no menos.

### "[Pregunta específica del tema]"
Respuesta: [Respuesta clara]

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~15 | Intro completada | Preguntas de contexto respondidas |
| ~30 | Demo terminada | Al menos 2 estudiantes comentaron |
| ~60 | Parte 1 del lab | Pedir manos arriba de quién tiene [X] |
| ~90 | Parte 2 del lab | Pasear y verificar pantallas |
| ~120 | Lab completado | Verificar checkpoints |
| ~150 | Reflexión | Al menos 3 estudiantes compartieron |

---

## Tips de Facilitación

### Si el grupo está callado:
- Hacer preguntas específicas a personas específicas (con respeto)
- "María, ¿en tu trabajo usan IA para algo?"
- Compartir tu propia experiencia primero

### Si alguien domina la conversación:
- "Excelente punto. ¿Alguien más tiene una perspectiva diferente?"
- Redirigir: "Guardemos eso para después. Ahora enfoquémonos en..."

### Si hay resistencia a la IA:
- Validar la preocupación: "Es una preocupación legítima"
- Redirigir: "El objetivo no es usar IA siempre, sino saber cuándo sí conviene"
- Mostrar ejemplos de uso responsable

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase vamos a [preview]. Lo que aprendieron hoy de [concepto] les va a servir para [aplicación futura]."

**Tarea para mencionar:**
[Descripción de la tarea asíncrona]
```

## Notas de Estilo

- **Tono**: Narrativo, mentor hablando a mentor
- **Párrafos**: Cortos (3-5 líneas máximo)
- **Emojis**: Solo en headers de sección
- **Ejemplos**: Conectados con trabajo real de profesionales
- **Datos**: Actualizados y verificados con WebSearch
- **Scripts**: Diálogos ejemplo listos para usar

## Analogías Recomendadas por Concepto

| Concepto | Analogía |
|----------|----------|
| LLM | Un pasante muy leído pero sin experiencia laboral |
| Prompt | Instrucciones a un asistente nuevo en su primer día |
| Context window | Memoria de trabajo (solo recuerda lo de esta conversación) |
| Hallucination | Cuando alguien "adorna" una historia para quedar bien |
| Temperature | Creatividad vs precisión (artista vs contador) |
| Token | Palabra o pedazo de palabra (unidad de lectura) |
| Fine-tuning | Entrenar a alguien para un rol específico |
| RAG | Darle un libro de referencia antes de responder |

## Contexto Actual Sugerido por Módulo

### Módulo 1: Fundamentos
- Estado actual de Claude, ChatGPT, Gemini
- Casos de uso empresarial reales
- Limitaciones conocidas y honestas

### Módulo 2: Superpoderes Aplicados
- Automatización en empresas reales
- ROI de implementar IA
- Tendencias de adopción

## Validación Final

- [ ] < 250 líneas
- [ ] Secciones de Conceptos, Analogías, Contexto, Errores, Checkpoints
- [ ] **Pregunta Detonadora: respuesta correcta + por qué las otras NO**
- [ ] Al menos 1 script de demo con plan B
- [ ] Checkpoints con tiempos que suman ~150 min
- [ ] Tips de facilitación para situaciones comunes
- [ ] Conexión explícita con clase siguiente
- [ ] Tono narrativo, párrafos cortos
- [ ] Preguntas frecuentes relevantes
