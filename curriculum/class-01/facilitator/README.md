# Guía del Facilitador - Sesión 01: Prompts efectivos

> Tiempo de lectura: 7 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Prompt**: la instrucción que le das a la IA; de su claridad depende la calidad de la respuesta.
- **Prompt profesional**: estructura Rol + Tarea + Contexto + Formato.
- **Output libre**: respuesta en texto natural, para que la lea una persona.
- **Output estructurado (JSON)**: respuesta en formato fijo, para que la procese otra app o flujo.

---

## 🔗 Analogías Útiles

**Prompt profesional ⟷ Briefing a un freelance:**
Nunca le dirías a un diseñador "hazme algo bonito". Le das rol (¿qué perfil?), tarea (¿afiche o post?), contexto (¿para qué marca?) y formato (¿tamaño, idioma?). La IA funciona igual.

**Output libre vs estructurado ⟷ Carta vs formulario:**
Una carta es linda para leer pero difícil de procesar. Un formulario tiene cada dato en su casilla — feo para leer, perfecto para que un sistema lo use. JSON es el formulario de la IA.

---

## 📚 Contexto para Compartir

### Por qué la estructura cambia tanto el resultado

El modelo predice la siguiente palabra más probable a partir de lo que le diste. Si le das poco ("escribe sobre productividad"), la respuesta probable es genérica. Si le das rol, tarea, contexto y formato, las palabras probables se anclan a TU caso. No es magia: es darle suficiente para acertar.

> **Para contar en clase:** "La IA no adivina lo que tienes en la cabeza. Si no se lo dices, rellena con lo más genérico que existe."

### Por qué importa el output estructurado

En la Sesión 4 estos prompts dejarán de leerse a ojo y empezarán a viajar dentro de un flujo de Make. Una app no puede "interpretar" un párrafo, pero sí puede leer un JSON con campos. Por eso hoy ya sembramos la diferencia.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "¿Por qué dos personas le piden casi lo mismo a la IA y reciben resultados tan distintos?"

**Respuesta esperada:** Porque una da estructura (rol, tarea, contexto, formato) y la otra no. La IA responde a lo que recibe, no a lo que imaginamos.

**Script post-respuestas:**
```
Facilitador: "Lo que cambia no es la IA — es el prompt.
Hoy aprendemos la anatomía que convierte una respuesta genérica en una que mandás tal cual."
```

### Demo Principal

**Qué mostrar:** el prompt genérico "Escribe sobre productividad" vs el mismo con Rol + Tarea + Contexto + Formato, en vivo.

**Script sugerido:**
```
Facilitador: "Le pido lo más genérico del mundo..."
[Envía "Escribe sobre productividad" — respuesta larga, genérica]
Facilitador: "¿Lo usarían hoy? No. Ahora miren con estructura."
[Envía la versión con rol + tarea + contexto + formato]
Facilitador: "Misma IA, otro resultado. Esto sí lo mando hoy mismo."
```

**Plan B (si Gemini falla o está lento):** ten capturas de las dos respuestas listas para pegar.

### Transición al Mini-proyecto

Muchos se bloquean en "¿qué tarea elijo?". Dales permiso de empezar con el ejemplo y adaptarlo.

**Script sugerido:**
```
Facilitador: "No busquen la tarea perfecta. Tomen las 3 de ejemplo —clasificar correo, resumir reunión, responder a un cliente—
y adáptenlas a lo que ustedes hacen. Lo importante es practicar la anatomía."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Las 3 preguntas de apertura"

Primeros 10 minutos, antes de teoría. Lanza al chat en orden:

```
1. "¿Qué tareas hacen todos los días que les quitan tiempo?"   (calibra casos reales)
2. "¿Usaron ChatGPT, Gemini o Claude? ¿Qué tal les fue?"        (calibra nivel del grupo)
3. "Si la IA hiciera UNA cosa por ustedes hoy, ¿cuál sería?"    (material para el mini-proyecto)
```

### Dinámica 2: "Prompt en voz alta"

Durante el mini-proyecto, pide que 2-3 lean su Prompt 1 en voz alta. Tu rol es señalar qué elemento falta:

```
Facilitador: "Buenísimo — ¿qué contexto le diste para que acierte?"
Estudiante: "...ninguno."
Facilitador: "Agrégalo. Ese dato es el que cambia la respuesta."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo: prompt débil vs fuerte (para la demo)

```
DÉBIL:  "Escribe sobre productividad."

FUERTE: "Actúa como gerente de operaciones. Dame 5 tips para que un equipo
         de 4 personas pierda menos tiempo en reuniones. Formato: lista
         numerada, máximo 25 palabras por tip, en español."
```

**Tip:** muestra cómo cada elemento (rol/tarea/contexto/formato) hace la respuesta más útil.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No sé qué tarea elegir" | No identifica una tarea concreta | Que use una de las 3 de ejemplo y la adapte |
| "Las respuestas me salen genéricas" | Falta contexto en el prompt | Pedir que agregue 1-2 datos específicos de su caso |
| "Copié el prompt y no funciona" | No reemplazó los bloques `<!-- ... -->` | Revisar que haya completado rol, contexto, etc. |
| "Gemini me pide iniciar sesión otra vez" | Cuenta institucional con restricciones | Usar cuenta personal de Gmail |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Puede señalar cuál de los 4 elementos (rol/tarea/contexto/formato) le falta a un prompt dado
- Mejora una respuesta agregando contexto, no escribiendo más texto
- Distingue cuándo conviene pedir texto libre y cuándo JSON

### El estudiante NECESITA AYUDA cuando:
- Copia el prompt de ejemplo sin adaptar los bloques `<!-- ... -->`
- Cambia muy poco entre intentos y no ve diferencia en el resultado

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Pueden nombrar los 4 elementos del prompt | Tomar 1 respuesta buena y seguir |
| 55 | Mini-proyecto listo | 3 prompts ejecutados en Gemini con resultados usables | Recortar a 2 prompts (clasificar + responder) |
| 60 | Cierre | Cada quien nombra la tarea que automatizará esta semana | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo está callado:** nombra 2-3 personas y pregúntales por su tarea recurrente; comparte tu propio ejemplo primero.
- **Si alguien domina:** "Guardemos ese caso para la Sesión 7, donde cada uno trabaja sobre el suyo."
- **Si terminan antes:** propón el Logro 🟢 (pedir el resultado en JSON) — siembra la Sesión 4.
- **Si se atrasan:** recorta a 2 prompts; el insight de la anatomía se mantiene.
- **Preguntas fuera de alcance:** "Eso lo vemos en la Sesión 3, cuando conectemos Gemini a Make."

---

## ❓ Preguntas Frecuentes

### P: ¿Necesito una cuenta de pago de Gemini?
**R:** No. La versión gratuita con tu cuenta de Google alcanza para toda la sesión.

### P: ¿Por qué pedir JSON si todavía no usamos Make?
**R:** Para que la idea ya esté sembrada. En la Sesión 4 ese JSON será lo que viaje dentro del flujo automático.

### P: ¿Sirve cualquier tarea o tiene que ser de oficina?
**R:** Cualquiera que el estudiante haga seguido. Mientras más real, mejor practica la anatomía.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| — | — | Es la primera sesión del curso |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "La próxima sesión entramos a Make y conectamos tu cuenta de Google. Vamos a armar el primer flujo automático real — y muy pronto, estos prompts dejarán de correrse a mano para ejecutarse solos dentro del flujo."

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos lograron 3 prompts con resultados realmente usables?
- ¿Qué tareas reales aparecieron? (material para casos en sesiones siguientes)
- ¿Alguien siguió obteniendo respuestas genéricas? (seguimiento antes de la Sesión 2)
