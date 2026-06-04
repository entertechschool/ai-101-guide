# Guía del Facilitador - Sesión 04: JSON + Parse JSON

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **JSON**: formato de datos en pares clave-valor (`{ "monto": 1500 }`) que las apps entienden.
- **System prompt**: instrucción que fija cómo responde la IA ("responde SOLO en JSON").
- **Data Structure**: el "molde" en Make que describe nombres y tipos del JSON.
- **Parse JSON**: módulo que convierte el texto JSON en variables mapeables.

---

## 🔗 Analogías Útiles

**JSON ⟷ formulario vs carta:**
Una carta cuenta todo en prosa; hay que leerla para sacar los datos. Un formulario tiene cada dato en su casilla. JSON es el formulario: la IA llena casillas, no escribe cartas.

**Data Structure ⟷ molde de gelatina:**
El molde define la forma que tendrá lo que entra. Si el JSON viene con la forma esperada, Make lo "desmolda" en variables limpias. Si viene deforme, avisa con un error.

**Parse JSON ⟷ separador de monedas:**
Le metes un puñado de monedas mezcladas (el texto JSON) y salen ordenadas por denominación (las variables: vendedor, monto, fecha). Listas para usar.

---

## 📚 Contexto para Compartir

### Por qué JSON y no texto libre

En la Sesión 3 Gemini devolvió un dato suelto. Funciona para uno, pero apenas necesitas cinco campos el texto libre se vuelve imposible de mapear con confianza. JSON resuelve esto: cada dato tiene una clave fija. Es el formato que usa el 99% de las APIs del mundo.

> **Para contar en clase:** "Pedirle a la IA que responda en JSON es la diferencia entre adivinar dónde está el monto y saber que siempre está en `monto`."

### El Data Structure protege el flujo

Sin molde, si la IA un día devuelve algo raro, el Sheet guarda basura en silencio. Con Data Structure, Make valida la forma y avisa. Es lo que separa un flujo "de juguete" de uno confiable.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "Cuando la IA te da una respuesta larga con varios datos adentro, ¿cómo los pasas a una tabla hoy?"

**Respuesta esperada:** copy/paste a mano, separando cada dato. Lento y propenso a errores.

**Script post-respuestas:**
```
Facilitador: "Eso que hacen a mano es justo lo que hoy automatizamos.
Le pedimos a la IA que ya nos entregue los datos separados, en JSON, y Make los reparte solos."
```

### Demo Principal

**Qué mostrar:** un correo informal → Gemini devuelve JSON → Parse JSON → fila estructurada en el Sheet, en vivo.

**Script sugerido:**
```
Facilitador: "Mando este correo: 'Ana cerró a Acme por 1500 soles, cliente nuevo'."
[Corre el escenario]
Facilitador: "Miren: Gemini lo convirtió en JSON, Parse lo separó, y cada dato cayó en su columna. Cero copy/paste."
```

**Plan B (si falla en vivo):** ten un escenario ya armado y una respuesta JSON de ejemplo para mostrar el Parse JSON.

### Transición al Mini-proyecto

**Momento crítico:** el Data Structure intimida. Muestra que "Generate from sample" lo crea casi solo pegando una respuesta de Gemini.

**Script sugerido:**
```
Facilitador: "No escriban el molde a mano. Copien una respuesta de Gemini, péguenla en 'Generate', y Make arma el Data Structure solo."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "¿JSON válido o no?"

Durante la teoría, muestra ejemplos y el grupo dice si es JSON válido:

```
{ "monto": 1500 }              → válido
{ monto: 1500 }                → inválido (falta comillas en la clave)
{ "monto": "1500", }           → inválido (coma final sobrante)
[ "Ana", "Acme", 1500 ]        → válido (array)
```

### Dinámica 2: "Diseña el molde"

Pide que, en una línea, escriban qué campos tendría el JSON de SU caso (no ventas). Sirve para la transferencia a su proyecto (Sesión 7).

---

## 💡 Ejemplos Listos para Usar

### System prompt que fuerza JSON

```
Devuelve SOLO un JSON con estos campos, sin texto adicional:
{ "vendedor": "", "cliente": "", "producto": "", "monto": 0, "fecha": "YYYY-MM-DD" }
```

**Tip:** "SOLO ... sin texto adicional" evita que Gemini envuelva el JSON en explicaciones que rompen el Parse.

### Respuesta de ejemplo para Generate Data Structure

```json
{ "vendedor": "Ana", "cliente": "Acme S.A.", "producto": "Consultoría", "monto": 1500, "fecha": "2026-06-01" }
```

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Parse JSON falla" | Gemini devolvió texto antes/después del JSON | Reforzar el prompt: "SOLO JSON, sin texto adicional" |
| "El monto llega como texto" | Tipo mal definido en el Data Structure | Poner `monto` como Number en el molde |
| "Faltan variables tras el Parse" | El Data Structure no incluye ese campo | Regenerar el molde con todos los campos |
| "La fecha sale rara" | Formato no ISO | Pedir `fecha` en `YYYY-MM-DD` en el prompt |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Explica por qué JSON es más confiable que texto libre
- Sabe que el Data Structure es el molde y para qué sirve
- Mapea las variables del Parse a las columnas sin dudar

### El estudiante NECESITA AYUDA cuando:
- La IA le devuelve texto envuelto y no refuerza el prompt
- Confunde el Data Structure con el Sheet
- No entiende de dónde salen las variables del Parse

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Reconocen JSON válido y para qué sirve el Data Structure | Repetir la dinámica "¿JSON válido?" |
| 55 | Mini-proyecto listo | Sheet `Ventas` recibe fila estructurada desde un correo | Usar el escenario pre-armado del facilitador |
| 60 | Cierre | Cada quien confirma su fila estructurada | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo se atrasa con el Data Structure:** usen "Generate from sample" todos al mismo tiempo.
- **Si alguien termina antes:** propón el Logro 🟡 (3 correos con formatos distintos).
- **Si el Parse falla en varios:** casi siempre es el prompt — refuerza "SOLO JSON".
- **Preguntas sobre documentos/reportes:** "Eso es la próxima sesión: convertir estos datos en documentos con plantillas."

---

## ❓ Preguntas Frecuentes

### P: ¿Tengo que saber programar para escribir JSON?
**R:** No. Solo reconocer la forma (claves y valores). Make y Gemini hacen el trabajo pesado.

### P: ¿Por qué no mapear directo sin Parse JSON?
**R:** Porque la salida de Gemini es texto. Parse JSON la convierte en variables separadas; sin él, tendrías un solo bloque de texto.

### P: ¿El Data Structure se reutiliza?
**R:** Sí. Una vez creado el molde "Venta", lo reutilizas en otros escenarios.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 01 | Output estructurado | Hoy lo formalizamos: el output estructurado es JSON |
| 03 | Gemini en Make | Antes extraía 1 dato; ahora devuelve varios en JSON |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "Ya tienes datos limpios y estructurados en el Sheet. La próxima sesión los convertimos en documentos: una plantilla con placeholders `{{variable}}` que se llena sola para generar reportes con formato profesional."

---

## 📊 Test Diagnóstico del Bloque

### Logística (opcional, ~15 min)

Si se aplica el test diagnóstico del primer bloque (Sesiones 1-4), proyéctalo al final de la sesión.

> "Es individual y a libro cerrado. **No afecta su calificación** — nos sirve para saber qué temas reforzar antes del proyecto integrador."

Las preguntas y la clave están en `test/`. Revisar en la siguiente sesión solo las preguntas con <60% de acierto.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos lograron la fila estructurada desde un correo?
- ¿El Parse falló por prompt o por molde? (patrón a reforzar)
- ¿Quiénes quedaron sin el escenario funcionando? (seguimiento antes de la Sesión 5)
