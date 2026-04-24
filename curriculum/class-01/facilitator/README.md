# Guía del Facilitador - Clase 01: Prompts y Gems

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **LLM**: modelo de IA que predice la siguiente palabra probable; no "piensa", calcula probabilidades.
- **Token**: unidad que procesa la IA (~3/4 de palabra en español); los planes gratuitos tienen límite medido en tokens.
- **Alucinación**: cuando la IA inventa datos (nombres, fechas, números) con apariencia creíble.
- **Prompt profesional**: estructura Rol + Contexto + Tarea + Formato + Restricciones.
- **Gem**: asistente personalizado de Gemini con instrucciones y archivos de referencia fijos.

---

## 🔗 Analogías Útiles

**Token <> Pieza de LEGO:**
Cada palabra que procesa la IA es una "pieza". Con el plan gratuito tienes una caja limitada al día. Frases largas consumen más piezas — la IA no cobra por tiempo, cobra por piezas.

**Prompt profesional <> Briefing a un freelance:**
Nunca le dirías a un diseñador freelance "hazme algo bonito". Le das rol (¿qué nivel?), contexto (¿para qué marca?), tarea (¿afiche o post?), formato (¿tamaño, idioma?) y restricciones (¿qué NO hacer?). La IA funciona igual.

**Gem <> Empleado con manual:**
Un Gem es como contratar a un empleado y entregarle un manual permanente ("eres X, trabajas para Y, usa siempre este tono"). No tienes que re-entrenarlo cada vez que le das una tarea.

---

## 📚 Contexto Histórico / Contexto Actual

### Gemini: de Bard a asistente con Gems

Google lanzó Bard en marzo 2023 como respuesta a ChatGPT. En febrero 2024 lo renombró Gemini y en 2024-2025 sumó Gems (asistentes personalizados), conectores con Google Workspace y API gratuita (1,500 req/día). Hoy compite de frente con Claude y ChatGPT.

La ventaja de Gemini para profesionales: integración nativa con Drive, Docs, Sheets y Gmail — sin salir del ecosistema que ya usan.

> **Para contar en clase:** "Cuando Google lanzó Gems en 2024, se volvió la primera IA con la que podés crear asistentes temáticos sin escribir una línea de código."

### Por qué "alucina" la IA

El corazón del LLM es un modelo de probabilidades. Si le preguntas "¿quién escribió el Quijote?", la palabra más probable después de "escribió" es "Cervantes" — acertó. Pero si le preguntas algo sin entrenamiento suficiente, el modelo igual completa con la palabra más probable, aunque no sea cierta. No distingue entre "saber" y "no saber" — solo completa.

> **Para contar en clase:** "La IA no miente a propósito. Simplemente no tiene un botón interno que diga 'no sé'."

**Fuentes:** [Google: Gemini Gems](https://support.google.com/gemini/answer/15235603){:target="_blank"}, [Anthropic: Why models hallucinate](https://www.anthropic.com/research){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "¿Por qué la IA 'alucina' (inventa datos que suenan creíbles)?"

**Respuesta esperada:** Porque predice palabras probables sin verificar contra una fuente de verdad. No tiene mecanismo interno de "no sé".

**Script post-respuestas:**
```
Facilitador: "Noten lo que acaban de decir: la IA no miente — solo sigue la palabra probable.
Por eso los detalles (fechas, nombres, números) son donde más alucina.
Hoy aprendemos a darle contexto suficiente para que la siguiente palabra probable sea la correcta."
```

### Demo Principal

**Qué mostrar:** el prompt "Escribe sobre productividad" y tus 3 variaciones propias en vivo. Usa tu propio rol como facilitador.

**Script sugerido:**
```
Facilitador: "Voy a pedirle a Gemini lo más genérico del mundo..."
[Envía "Escribe sobre productividad" — respuesta larga, genérica]
Facilitador: "¿Lo usarían hoy? No. Es genérico."
[Envía variación 3 con Rol + Contexto + Tarea + Formato + Restricciones]
Facilitador: "¿Notaron la diferencia? Esto sí lo mando hoy mismo."
```

**Plan B (si Gemini falla o está lento):** tener capturas de pantalla de las 3 variaciones listas para pegar.

### Transición al Lab

**Momento crítico:** muchos estudiantes se bloquean en la Actividad 2 (brief) porque "no saben qué automatizar". Tenés que darles permiso de escribir un brief imperfecto.

**Script sugerido:**
```
Facilitador: "No necesitan el brief perfecto. Necesitan UN brief.
Si no están seguros, usen el caso Roberto de referencia, o el primero que se les ocurra.
Lo van a refinar en la clase 6. Lo importante hoy es tener algo escrito."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Las 3 preguntas de apertura"

Contexto: primeros 10 minutos, antes de teoría.

Lanzás 3 preguntas al chat en este orden:

```
Facilitador: "1. ¿Cuántas veces al mes usás IA? Rangos: 0 / 1-5 / 5-20 / 20+"
(Leer respuestas — calibra el nivel del grupo)

Facilitador: "2. ¿Qué esperás que la IA te solucione? Una frase."
(Esto lo retomás al final de la clase para confrontar expectativa vs realidad)

Facilitador: "3. ¿Cuál es la tarea que más tiempo te quita cada semana?"
(Esto es material directo para la Actividad 2 — el brief)
```

### Dinámica 2: "Brief en voz alta"

Contexto: durante la Actividad 2, antes del checkpoint.

Pedís que 2-3 estudiantes lean su brief en voz alta. Tu rol es señalar qué elemento falta:

```
Facilitador: "Excelente — ¿quién recibe ese reporte?"
Estudiante: "...no lo dije."
Facilitador: "Perfecto, agrégalo. Ese dato es crítico para la clase 6."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Brief de gerente comercial (caso Roberto)

**Cuándo usarlo:** como ejemplo vivo cuando un estudiante pregunta "¿qué tan específico tiene que ser?"

```
Quiero automatizar el reporte semanal de ventas que genero cada viernes,
dirigido a mis 3 vendedores y al gerente general,
que incluye ventas totales, clientes nuevos y hallazgos por vendedor,
para ahorrar 4 horas semanales.
```

**Tip:** muestra cómo cada elemento (qué/cuándo/quién/datos/tiempo) es específico, no abstracto.

### Ejemplo 2: Instrucciones mínimas de Gem para demo

**Cuándo usarlo:** durante la demo de Gem, si el estudiante no sabe qué poner.

```
Eres mi asistente del curso AI 101.
MI PROYECTO: Automatizar reporte semanal de ventas (caso Roberto).
TU ROL: ayudarme a diseñar prompts, estructuras y textos.
TONO: directo, práctico, español latinoamericano.
```

**Tip:** menos es más. Un Gem con 5 líneas bien pensadas supera uno con 50 líneas vagas.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No entiendo qué brief escribir" | El estudiante no identifica una tarea concreta | Pedirle que piense en su último viernes: ¿qué reporte armó a mano? |
| "Mi Gem responde genérico" | Las instrucciones no incluyen el brief completo | Abrir el Gem y verificar que el campo "Instrucciones" tenga el brief pegado |
| "No puedo subir archivo al Gem" | Formato no soportado o archivo >10 MB | Convertir a PDF o reducir tamaño |
| "Las 3 variaciones del prompt dan respuestas iguales" | El estudiante cambió poco entre versiones | Forzar que la V3 tenga restricciones muy explícitas (número de palabras, formato) |
| "Gemini me pide iniciar sesión otra vez" | Sesión expirada o cuenta institucional con restricciones | Pedir que usen cuenta personal de Gmail |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Puede explicar por qué la IA alucina sin mencionar "errores" o "bugs"
- Puede identificar cuál de los 5 elementos (Rol/Contexto/Tarea/Formato/Restricciones) le falta a un prompt dado
- Su Gem responde con contexto de SU proyecto, no con respuestas genéricas

### El estudiante NECESITA AYUDA cuando:
- Copia el prompt de ejemplo sin adaptar los bloques `<!-- ... -->`
- Se queda trabado en "¿qué automatizo?" por más de 10 min
- Su Gem responde como el chat normal (señal de que no guardó las instrucciones)

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 15 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 35 | Teoría terminada | Pregunta Quiz Pre-Lab respondida | Tomar 1 respuesta buena y seguir |
| 70 | Actividad 1 lista | 3 prompts visibles en Gemini por estudiante | Ofrecer el prompt "battery" — cambiar tema si no aparecen variaciones |
| 105 | Actividad 2 lista | Brief en Google Doc con los 4 elementos | Si falta destinatario o tiempo, pedir agregarlo ahí mismo |
| 145 | Actividad 3 lista | Gem respondiendo con contexto del brief | Revisar que el campo "Instrucciones" del Gem tenga el brief |
| 150 | Cierre | Reflexión + compromiso de usar el Gem 3 veces esta semana | — |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Nombrar específicamente 2-3 personas y preguntarles por su tarea recurrente.
- Compartir TU propio brief como instructor primero.

### Si alguien domina la conversación:
- "Excelente — guardemos ese caso para la clase 7 donde cada uno trabaja sobre el suyo."

### Si la mayoría termina antes:
- Proponer el Logro Adicional 🟡 (biblioteca de 5 prompts).

### Si la mayoría se atrasa:
- Recortar la Actividad 1 a 2 variaciones (V1 y V3). El insight del contraste igual se mantiene.

### Si hay preguntas fuera de alcance:
> "Excelente pregunta. Eso lo vemos en la clase 5 cuando conectemos Gemini API a Make."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Sugerir Logro 🔴 (probar el Gem con un caso límite, observar alucinaciones).
- Rol de mentor de pares durante la Actividad 3.

### Para estudiantes con dificultades:
- Usar el caso Roberto como su brief inicial. Pueden personalizar en la clase 7.
- Sentarse con ellos 3-4 minutos durante la Actividad 3 para configurar el Gem paso a paso.

---

## ❓ Preguntas Frecuentes

### P: ¿Qué pasa si no tengo un "reporte real" que automatizar?
**R:** Usá el caso Roberto (reporte semanal de ventas) como tu brief inicial. En la clase 7 lo vas a personalizar. Lo importante hoy es practicar la estructura, no tener el caso perfecto.

### P: ¿El Gem funciona con la cuenta gratuita?
**R:** Sí, Gems es gratis. El límite está en el uso de Gemini (cantidad de mensajes al día), no en cuántos Gems podés crear.

### P: ¿Puedo subir varios archivos al Gem?
**R:** Sí, hasta 10 archivos por Gem en plan free. Recomiendo empezar con 1 y agregar según necesidad.

### P: ¿Qué pasa si pierdo la cuenta de Google que usé para el Gem?
**R:** El Gem está atado a tu cuenta de Google. Recomiendo usar la cuenta personal, no una laboral que pueda cerrarse.

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| — | — | Es la primera clase del curso |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase vamos a diseñar el Google Sheet de tu proyecto con 3 pestañas. Le vamos a pedir al Gem que te acaba de ayudar hoy que te sugiera columnas, datos de ejemplo y parámetros. El brief y el Gem que construiste hoy son la base de todo."

**Pre-work / Tarea implícita:** usar el Gem al menos 3 veces en la semana en tareas reales. Si hace algo mal, tomar nota — eso vamos a corregir en clase 6.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes terminaron con un Gem respondiendo con contexto real?
- ¿Qué briefs fueron los más genéricos? (seguimiento en clase 2)
- ¿Quiénes identificaron tareas de automatización realmente valiosas? (candidatos a mentores de pares)
- ¿Algún estudiante se quedó bloqueado en "qué automatizar"? (seguimiento 1 a 1 antes de clase 2)
