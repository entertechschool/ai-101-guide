# Guía del Facilitador - Clase 05: Gemini API + 2 flujos completos

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **API**: forma en que un programa habla con otro; Gemini API permite que Make llame a Gemini.
- **API Key**: credencial única; es una contraseña — no se comparte nunca.
- **HTTP POST**: método para enviar datos; Make lo hace con el módulo HTTP Make a Request.
- **JSON**: formato `{clave: valor}` que APIs entienden.
- **Módulo HTTP**: módulo genérico de Make para llamar cualquier API.
- **Rate limit**: 1,500 req/día, 15/min en plan gratuito de Gemini — suficiente para el curso.

---

## 🔗 Analogías Útiles

**API <> mozo del restaurante:**
Tu flujo (Make) es el comensal que pide "un plato con datos estructurados". El mozo (API) toma el pedido, lo lleva a la cocina (Gemini), y trae el plato de vuelta. Nunca entrás a la cocina directamente — siempre pasa por el mozo.

**API Key <> tu tarjeta de cliente:**
Cada vez que hacés un pedido, el mozo anota cuántas veces viniste hoy. Si superás tu cuota (1,500 req/día), te dice "mañana volvés". Por eso nunca compartís tu tarjeta: alguien más consumiría tu cuota.

**JSON <> formulario bien llenado:**
Si le pedís al mozo "decile al cocinero lo que quiero" sin estructura, el mozo improvisa. Si le das un formulario `{plato: "arroz", punto: "medio"}`, el cocinero sabe exactamente qué hacer. JSON es ese formulario.

---

## 📚 Contexto Histórico / Contexto Actual

### Gemini API: la bajada a pymes del acceso a IA

OpenAI abrió acceso a GPT-3 por API en 2020 pero con costos prohibitivos para PYMEs. En 2023-2024, Google respondió con Gemini API y un plan gratuito sustancial (1,500 req/día) sin requerir tarjeta. Resultado: automatizaciones con IA dejaron de ser exclusivas de empresas con presupuesto tech.

> **Para contar en clase:** "Lo que en 2022 costaba $500/mes por automatización con IA, hoy corre gratis con Gemini API. La democratización es real — ustedes la están aprovechando en esta clase."

### Por qué JSON se volvió el idioma universal de APIs

JSON (JavaScript Object Notation) se estandarizó en 2009 y desplazó a XML por ser más ligero y legible. Hoy, el 95% de APIs modernas usan JSON como formato principal. Para no-code, implica que aprender a leer JSON una vez te abre 1,500+ integraciones de Make.

> **Para contar en clase:** "Aprender JSON es como aprender el alfabeto de la automatización. Una vez que lo leés, el 95% de APIs se abren para vos."

**Fuentes:** [Gemini API docs](https://ai.google.dev/gemini-api/docs){:target="_blank"}, [JSON oficial](https://www.json.org/){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "Cuando leés un correo informal de un vendedor, ¿qué 'datos' extraes mentalmente sin pensarlo?"

**Respuesta esperada:** Fecha, nombres, monto, tipo de producto/servicio, contexto.

**Script post-respuestas:**
```
Facilitador: "Exacto — ustedes extraen esos datos en medio segundo sin pensar.
Hoy enseñamos a Gemini a hacer lo mismo. El truco está en describirle qué datos extraer."
```

### Demo Principal

**Qué mostrar:** en Google AI Studio, un correo informal → prompt con JSON schema → respuesta JSON de Gemini → cómo ese JSON mapea a las columnas del Sheet.

**Script sugerido:**
```
Facilitador: "Este es un correo real que reciben en una empresa."
[Muestra correo: "Hola, hoy Juan cerró a Industrias López por 3500..."]
Facilitador: "Sin IA, alguien tiene que leerlo y escribirlo en el Sheet manualmente."
[Muestra prompt + respuesta JSON en AI Studio]
Facilitador: "Con este prompt, Gemini lo hace en 3 segundos. Hoy conectamos eso a Make."
```

**Plan B (si AI Studio no carga):** tener capturas del prompt y la respuesta JSON como fallback.

### Transición al Lab

**Momento crítico:** configurar la API key en Make. Si lo hacen mal, todo falla en cadena.

**Script sugerido:**
```
Facilitador: "La API key va al final de la URL, después de '?key='.
Ejemplo: https://...generateContent?key=TU_KEY_AQUI
NUNCA en el body, NUNCA en los headers. Solo al final de la URL."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Caza el JSON en la respuesta"

Contexto: cuando Parse JSON falla por primera vez.

Proyectás una respuesta de Gemini mal formateada (con texto introductorio):

```
"Claro, aquí está el JSON que solicitaste:
{ "fecha": "2026-04-19", ...}"
```

```
Facilitador: "¿Qué hay de más que hace fallar a Parse JSON?"
(Respuesta: el texto antes del {)
Facilitador: "¿Cómo lo arreglamos sin cambiar el módulo?"
(Respuesta: modificar el prompt: 'responde SOLO el JSON, sin texto adicional')
```

### Dinámica 2: "El prompt que inventa datos"

Contexto: durante la Actividad 1, si alguien ve que Gemini "alucinó" un dato.

```
Facilitador: "¿Alguien tuvo un caso donde Gemini inventó un dato?"
[Si hay ejemplo]
Facilitador: "Miren — el correo no decía la fecha, pero Gemini puso una.
¿Por qué? Porque el campo fecha es obligatorio en el schema.
Cómo prevenir: agregar al prompt 'si un campo no está en el correo, déjalo como null'."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Prompt estricto para extracción (caso genérico)

**Cuándo usarlo:** si un estudiante tiene problemas con Parse JSON fallando.

```
Eres un asistente que extrae datos de correos. Responde SOLO JSON válido,
sin texto introductorio, sin markdown, sin explicaciones.

Si un campo no está en el correo, usa null.
Si hay ambigüedad, prefiere null a inventar.

Campos requeridos:
{ "fecha": "YYYY-MM-DD" | null,
  "monto": number | null,
  ... }

CORREO:
[cuerpo del correo aquí]
```

**Tip:** el párrafo "Si un campo no está en el correo, usa null" reduce 90% de alucinaciones.

### Ejemplo 2: Prompt para insights semanales (caso Roberto)

**Cuándo usarlo:** Actividad 2, para el Escenario 2.

```
Eres un analista de ventas senior. Analiza los datos de esta semana y devuelve
SOLO JSON válido con exactamente estos campos:

{ "resumen_ejecutivo": "párrafo de 2-3 oraciones",
  "hallazgo_1": "observación específica con números",
  "hallazgo_2": "...",
  "hallazgo_3": "...",
  "riesgo_1": "algo que preocupa",
  "riesgo_2": "...",
  "oportunidad_1": "algo a aprovechar",
  "accion_1": "próximo paso concreto",
  "accion_2": "..." }

REGLAS:
- Cada hallazgo debe comparar contra meta o semana anterior
- Siempre incluye números específicos
- Explica causa probable cuando la haya
- Responde en español latinoamericano

DATOS SEMANA:
[datos del Sheet aquí]

META SEMANAL: [de Config]
SEMANA ANTERIOR: [de Historico]
```

**Tip:** este prompt se mejora mucho en Clase 6 con few-shot; hoy es la versión base.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "401 Unauthorized" | API key incorrecta o mal ubicada | Copiar key limpia de AI Studio, ponerla al final de URL con `?key=` |
| "Parse JSON failed" | Gemini respondió con texto extra | Agregar al prompt "responde SOLO JSON, sin markdown" |
| "429 Rate limit" | Superaste 15 req/min o 1,500/día | Esperar 1 min; si es límite diario, esperar al siguiente día |
| "Marcadores tipo IA siguen literales" | Replace Text mapea al campo equivocado del Parse JSON | Verificar nombres exactos (`{{parse.hallazgo_1}}` no `{{parse.hallazgos[0]}}`) |
| "PDF desbordado" | Texto de Gemini muy largo | Agregar al prompt "máximo 25 palabras por campo" |
| "Gemini responde en inglés" | No especificaste idioma | Agregar al prompt "responde en español latinoamericano" |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Explica con sus palabras por qué el prompt debe decir "SOLO JSON"
- Distingue entre modificar el prompt vs agregar módulos Make para resolver un problema
- Predice qué marcador de su plantilla se va a beneficiar más de optimización de prompt en C06

### El estudiante NECESITA AYUDA cuando:
- Copia-pega el prompt sin adaptar a su caso
- No sabe dónde copiar la API key en el módulo HTTP
- No entiende por qué Parse JSON está separado del HTTP

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura terminada | Todos con API key abierta en otra pestaña | Si no tienen, dar 2 min para obtenerla |
| 30 | Teoría terminada | Primera llamada exitosa en AI Studio | Demo pregrabada si el playground se cae |
| 75 | Actividad 1 | Gemini procesa 3 correos y Sheet recibe filas estructuradas | Revisar prompt estricto + mapping de Parse JSON |
| 120 | Actividad 2 | PDF con marcadores tipo IA llenos | Si falla, simplificar prompt: pedir solo 3 marcadores en vez de 9 |
| 150 | Actividad 3 | Escenario 2 con scheduled activo + Historico recibiendo fila | — |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Pedir que 2-3 estudiantes compartan pantalla con su AI Studio y muestren respuestas JSON reales.
- Retomar la columna Descripción de Clase 2: "Este es el momento en que esa columna cobra sentido."

### Si alguien domina la conversación:
- Pedirle que explique al grupo cómo resolvió un problema específico (mentoría cruzada).

### Si la mayoría termina antes:
- Logro 🟡 (few-shot en el prompt) — preview de C06.
- Logro 🔴 (prompt como variable de Make).

### Si la mayoría se atrasa:
- Reducir objetivo a Escenario 1 funcionando solamente; Escenario 2 queda como tarea.
- Priorizar que al menos tengan 3 marcadores tipo IA llenos (no los 9).

### Si hay preguntas fuera de alcance:
> "Buena pregunta. Prompt engineering avanzado lo vemos la próxima clase."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logro 🔴 (prompt como variable) + ayudar compañeros rezagados con Parse JSON.
- Proponer experimentar con modelo `gemini-2.0-flash-thinking-exp` y comparar.

### Para estudiantes con dificultades:
- Ofrecer el prompt completo pre-probado como template.
- Sentarse con ellos 5-10 min durante Actividad 1 para configurar el primer HTTP + Parse JSON juntos.

---

## ❓ Preguntas Frecuentes

### P: ¿La API key funciona en todos los modelos de Gemini?
**R:** Sí, misma key sirve para gemini-2.0-flash, flash-thinking, pro, etc. Cada modelo tiene rate limits y costos distintos, pero en plan free la key es única.

### P: ¿Qué pasa si supero los 1,500 req/día?
**R:** El siguiente request da error 429. Reseteo a las 00:00 PT. Para el curso no vas a llegar ni al 10% de ese límite.

### P: ¿Puedo usar esta key en otros proyectos?
**R:** Sí, pero cada llamada consume de la misma cuota diaria. Recomiendo una key por proyecto para aislar consumo.

### P: ¿Qué pasa si Gemini responde algo que no es JSON?
**R:** Parse JSON fallará y el flujo se detiene en ese módulo. Solución: ser más estricto en el prompt ("SOLO JSON, sin markdown, sin texto adicional").

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| 01 | Prompt profesional | Hoy los prompts tienen formato JSON structured |
| 02 | Columna Descripción | Ahora cobra sentido: es el input principal para Gemini |
| 03 | Marcadores tipo 3 | Hoy se llenan por primera vez |
| 04 | Escenarios Make | Hoy se les agrega HTTP + Parse JSON |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase optimizamos los prompts que configuraron hoy. Van a ver cómo el mismo prompt, reescrito con chain-of-thought y few-shot, transforma insights 'planos' en insights 'potentes'. También aplicamos 4 mejores prácticas del sistema (nombres con fecha, backups, alertas, logs). Y definimos el plan de personalización para su caso real de Clase 7."

**Pre-work / Tarea implícita:** anotar 2-3 insights que Gemini generó hoy y que sintieron "planos". En Clase 6 los van a mejorar con optimización de prompts.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes tienen los 2 escenarios activos al cerrar?
- ¿Hubo casos donde Parse JSON falla consistentemente? (problema de prompt a resolver en C06)
- ¿Los insights generados son coherentes con los datos del Sheet? (predicción de satisfacción en Demo Day)
- ¿Alguno se quedó sin API key funcionando? (seguimiento 1 a 1 antes de C06)
