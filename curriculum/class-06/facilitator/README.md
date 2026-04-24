# Guía del Facilitador - Clase 06: Integración total y mejores prácticas

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Chain of thought (CoT)**: pedir a la IA que "piense paso a paso" antes de responder.
- **Few-shot**: incluir 1-3 ejemplos de output deseado dentro del prompt.
- **Persona**: definir un rol específico con años de experiencia ("analista senior con 10 años").
- **Storytelling de datos**: números + comparación + causa + acción = insight potente.
- **Error handler**: módulo de Make que reacciona cuando algo falla (Resume, Rollback, Ignore).
- **Log**: fila por ejecución con estado, timestamp y duración.

---

## 🔗 Analogías Útiles

**Prompt plano vs optimizado <> telegrama vs carta:**
Telegrama: "Ventas bajaron". Carta: "Las ventas cayeron 8% la última quincena, principalmente por la salida del cliente ABC que representaba 15% del pipeline. Acción: priorizar reposición con los leads calificados de Juan." Misma info, diferente impacto.

**Few-shot <> mostrar ejemplos al nuevo empleado:**
Si le decís a un nuevo "escribe un buen insight", lo hará como pueda. Si le mostrás 2 ejemplos de insights que te gustan, los replica. Gemini funciona igual.

**4 mejores prácticas <> cinturón de seguridad + airbag + freno ABS + luces:**
Cada una aporta poco sola. Juntas, la diferencia entre "funciona" y "sobrevive años". Nadie pone solo el airbag y nada más.

---

## 📚 Contexto Histórico / Contexto Actual

### Chain of thought: la técnica que cambió el prompt engineering

En 2022, el paper "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models" mostró que pedirle a una IA "piensa paso a paso antes de responder" mejora dramáticamente tareas de razonamiento. Hoy es técnica estándar en cualquier prompt de producción.

> **Para contar en clase:** "Lo que acabás de agregar a tu prompt — las palabras 'piensa paso a paso' — es una técnica que Google publicó en 2022 y cambió cómo usamos LLMs."

### Few-shot learning: la forma humana de enseñar

Los humanos aprendemos mostrando ejemplos, no dando reglas abstractas. Los LLMs modernos funcionan igual. 2-3 ejemplos en el prompt producen salidas más consistentes que 10 líneas de instrucciones. Descubrimiento clave de GPT-3 (2020) que hoy es estándar.

> **Para contar en clase:** "Un solo ejemplo bien elegido en el prompt hace más por la consistencia que 5 párrafos de reglas."

**Fuentes:** [Google prompt engineering guide](https://ai.google.dev/gemini-api/docs/prompting-strategies){:target="_blank"}, [CoT paper](https://arxiv.org/abs/2201.11903){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "De los insights que Gemini generó ayer, ¿cuáles sentiste que eran útiles y cuáles tibios? ¿Qué les faltaba a los tibios?"

**Respuesta esperada:** faltan números, comparación, causa, acción.

**Script post-respuestas:**
```
Facilitador: "Perfecto — acaban de identificar exactamente qué vamos a agregar hoy
con persona, few-shot y chain-of-thought. No vamos a cambiar la IA, vamos a cambiar
cómo le hablamos."
```

### Demo Principal

**Qué mostrar:** tu Escenario 2 corriendo 2 veces — una con prompt v1 (el de Clase 5) y otra con prompt v2 (optimizado). Mostrar PDFs lado a lado.

**Script sugerido:**
```
Facilitador: "Este es el mismo input de datos. Dos prompts distintos."
[Muestra PDF v1: "Las ventas fueron 21,700 esta semana."]
[Muestra PDF v2: "21,700 (108% de meta, +12% vs anterior), impulsado por..."]
Facilitador: "Mismos datos, misma IA. La diferencia es 10 minutos de optimización del prompt."
```

**Plan B:** tener los 2 PDFs pre-generados como capturas listas para proyectar.

### Transición al Lab

**Momento crítico:** los estudiantes pueden agobiarse con el prompt largo de la Actividad 1. Darles permiso de adaptar, no copiar.

**Script sugerido:**
```
Facilitador: "El prompt v2 que les muestro es largo — 20 líneas.
NO lo copien literal. Adáptenlo a SU caso. Pero mantengan la estructura:
Persona → Contexto → Reglas → Ejemplo → Instrucciones CoT → JSON esperado."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Detector de storytelling"

Contexto: durante la teoría.

Lanzás insights y el grupo clasifica:

```
Facilitador: "Las ventas subieron."
[Grupo: PLANO]
Facilitador: "Las ventas subieron 12%."
[Grupo: MEDIOCRE — falta contra qué comparar]
Facilitador: "Las ventas subieron 12% vs la meta semanal, gracias a la renovación de ABC."
[Grupo: POTENTE]
```

### Dinámica 2: "El error handler invisible"

Contexto: antes de la Actividad 2.

```
Facilitador: "Imaginen que el viernes se va la luz 10 minutos justo a las 4pm.
Su scheduled trigger corre, falla en el HTTP, y nadie se entera.
¿Cómo sabrían que no salió el reporte?"
[Toma respuestas]
Facilitador: "Exacto — sin error handler, no te enterás. Por eso hoy lo agregamos."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Plantilla de prompt optimizado

**Cuándo usarlo:** si un estudiante dice "no sé cómo estructurar el v2".

```
[PERSONA]: Eres un [rol] senior con [años] de experiencia en [industria].
           Tu estilo es [adjetivos: directo, basado en datos, accionable].

[CONTEXTO DEL NEGOCIO]:
- [Meta o benchmark clave]
- [Semana/período anterior]

[REGLAS DEL ANÁLISIS]:
1. Cada [elemento] DEBE [criterio verificable]
2. Cada [elemento] DEBE [criterio verificable]
3. ...

[EJEMPLO de buen output]:
"[Ejemplo concreto con 2-3 oraciones que cumple todas las reglas]"

[DATOS]:
{{datos_del_sheet}}

[INSTRUCCIONES]:
Piensa paso a paso:
1. Identifica los fenómenos más notables
2. Encuentra datos específicos
3. Formula acciones

Responde SOLO JSON: { ... }
```

**Tip:** la estructura es 5 bloques. Si algún bloque está vacío en el prompt del estudiante, ahí está la oportunidad de mejora.

### Ejemplo 2: Error handler con alerta

**Cuándo usarlo:** si alguien pregunta cómo configurar.

```
Click derecho en módulo HTTP → Add error handler → Resume (no Rollback)
  ↓
[Gmail — Send an Email]
  To: tu correo
  Subject: ❌ Error en flujo del reporte — {{formatDate(now; "YYYY-MM-DD HH:mm")}}
  Body: El módulo [HTTP Gemini] falló. Revisar Make History.
         Timestamp: {{now}}
         Escenario: [nombre del escenario]
```

**Tip:** "Resume" hace que el flujo continúe después del error (útil si solo falla 1 módulo). "Rollback" cancela toda la ejecución.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Gemini sigue dando insights planos" | Prompt no incluye few-shot (ejemplo) | Agregar bloque "[EJEMPLO de buen output]: ..." |
| "formatDate da error" | Sintaxis mal escrita | Copiar exacto: `{{formatDate(now; "YYYY-MM-DD")}}` con punto y coma |
| "Error handler no se activa" | En modo Rollback por default | Cambiar a Resume desde el menú del handler |
| "Logs no recibe fila" | Módulo Add a row no conectado al flujo principal | Arrastrar conexión desde el último módulo al Logs |
| "El prompt v2 da respuesta en inglés" | No se conservó "español latinoamericano" | Agregar al bloque de reglas explícitamente |
| "Los 5 puntos de personalización son genéricos" | Estudiante no conectó con su caso real | Forzar ejemplo específico: "¿Qué columna específica cambiarías?" |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Puede explicar por qué un insight con comparación es más potente que uno con solo números
- Distingue "error handler Resume" vs "Rollback" y cuándo usar cada uno
- Tiene un plan de personalización con ejemplos específicos (no genéricos)

### El estudiante NECESITA AYUDA cuando:
- Copia el prompt v2 sin adaptar el rol ni el contexto
- No entiende por qué agregar un ejemplo mejora la calidad
- Sus 5 puntos de personalización son iguales a Roberto

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura | Respuestas de pregunta detonadora | Avanzar con 2-3 respuestas |
| 25 | Teoría terminada | Quiz de COMPROBACIÓN correcto | Reforzar con 1 ejemplo extra |
| 70 | Actividad 1 | 3 prompts reescritos + screenshots antes/después | Revisar que el v2 tenga los 5 bloques |
| 110 | Actividad 2 | 4 mejores prácticas visibles | Ir una por una si les cuesta |
| 140 | Actividad 3 | Plan personalización con ejemplos concretos | Forzar ejemplos específicos ("¿qué columna cambiarías?") |
| 150 | Cierre | Reflexión + preview de Clase 7 | — |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Pedir que un estudiante lea su prompt v1 en voz alta, y el grupo sugiere una mejora.
- Compartir tu propio prompt optimizado como referencia.

### Si alguien domina la conversación:
- Pedirle que lea sus 5 puntos de personalización. Eso calienta al resto para escribir los suyos.

### Si la mayoría termina antes:
- Logro 🟢 (optimizar también el prompt del flujo instantáneo).
- Logro 🟡 (dashboard de Logs).

### Si la mayoría se atrasa:
- Priorizar Actividad 1 completa; Actividad 2 reducirla a 2 prácticas (fecha + error handler).
- Dejar plan de personalización (Actividad 3) como pre-trabajo de C7.

### Si hay preguntas fuera de alcance:
> "Buena pregunta. Lo aplicás en tu caso real la próxima clase."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logro 🔴 (probar modelo flash-thinking vs flash).
- Proponer que optimicen 5 prompts en vez de 3.

### Para estudiantes con dificultades:
- Ofrecer el prompt v2 pre-escrito como template (adaptan rol y contexto).
- Ayudarles a configurar el error handler y el formatDate juntos.

---

## ❓ Preguntas Frecuentes

### P: ¿Cuántos ejemplos dar en few-shot?
**R:** 1-3 ejemplos. Más de 5 y el prompt se vuelve largo sin aportar más calidad. 2 es el sweet spot.

### P: ¿Chain of thought funciona con cualquier modelo?
**R:** Sí, pero mejor con modelos grandes. Con flash-thinking ya lo hace automáticamente.

### P: ¿El error handler consume operaciones extras?
**R:** Solo cuando se activa. Si el flujo no falla, 0 ops extra. Cuando falla, 1-2 ops para la alerta.

### P: ¿Puedo tener múltiples error handlers?
**R:** Sí. Uno por módulo frágil es ideal — Gemini HTTP (API puede caer) y Sheets (permisos pueden cambiar).

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| 01 | Prompt profesional | Hoy agregamos técnicas avanzadas sobre esa base |
| 05 | Gemini API + JSON | Hoy optimizamos el prompt que configuramos ayer |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase es acompañamiento 1 a 1. Cada uno de ustedes construye su sistema propio con su caso real. Los 5 puntos de personalización que escribieron hoy son su roadmap. Lleguen con datos reales a mano — si no los tienen, inventen simulados antes de la clase."

**Pre-work / Tarea implícita:** preparar 3-5 registros reales de su trabajo para usar en la Clase 7. Si no hay reales, crear simulados que reflejen el tipo y volumen real.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes lograron diferencia clara en los insights antes/después?
- ¿Los 5 puntos de personalización de cada uno son específicos o genéricos?
- ¿Quiénes siguen sin tener datos reales para C7? (mandar recordatorio por chat)
- ¿Hay casos muy diferentes a Roberto que requieran preview especial? (agendar 15 min 1 a 1 antes de C7)
