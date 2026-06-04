> **Sesión 4 de 8** · JSON + Parse JSON

# Sesión 04: JSON + Parse JSON

## Resumen

En la sesión pasada Gemini extrajo un solo dato en texto libre. Hoy aprendes a pedirle **varios datos a la vez, ordenados** — y a recibirlos dentro del flujo en formato **JSON**, el lenguaje estándar de datos que las apps entienden. Entenderás qué es JSON (objetos, arrays, pares clave-valor) y por qué pedirle a la IA que responda en JSON convierte una respuesta frágil en una robusta.

Luego conocerás dos piezas clave de Make: el **Data Structure** (el "molde" que describe cómo viene el JSON) y el módulo **Parse JSON** (que convierte ese texto en variables que puedes arrastrar a cada columna). Al terminar, cuando un vendedor envía un correo informal con una venta, Gemini devuelve JSON y cada campo —vendedor, cliente, producto, monto, fecha— cae solo en su columna del Sheet.

---

## ¿Por qué te sirve?

- **JSON es cómo la IA "habla" con cualquier sistema.** Dominarlo te abre la puerta a conectar IA con casi cualquier herramienta, no solo Sheets.
- **Pedir respuestas estructuradas elimina el copy/paste manual.** En vez de leer un texto y separar datos a mano, cada campo llega en su lugar.
- **El Data Structure hace tu flujo confiable.** Si la IA devuelve algo fuera del molde, Make avisa con un error claro en vez de guardar basura.

---

## 🎯 ¿Qué haremos en clase?

1. **Entenderás qué es JSON** — objetos, arrays y pares clave-valor.
2. **Aprenderás a pedirle JSON a la IA** desde el system prompt y por qué es más robusto que el texto libre.
3. **Crearás un Data Structure en Make** — el molde que describe el JSON esperado.
4. **Usarás Parse JSON** para convertir la respuesta en variables y mapear cada campo a su columna en el caso "ventas desde Gmail".

---

## Objetivos de Aprendizaje

Al finalizar esta sesión, podrás:

1. **Explicar** qué es JSON y por qué conviene que la IA responda en ese formato.
2. **Escribir** un system prompt que obligue a la IA a responder en JSON con campos definidos.
3. **Crear** un Data Structure en Make que describa la estructura del JSON.
4. **Procesar** la respuesta con Parse JSON y mapear cada variable a una columna del Sheet.

---

## ✅ Preparación para la Clase

### De sesiones anteriores

- Tu escenario con Gemini funcionando (Sesión 3), extrayendo al menos un dato.
- Conexión Gemini (Connection) y conexión Google activas en Make.

### Reflexión previa

Antes de llegar a clase, piensa en:

- ¿Qué información recibes en texto libre (correos, mensajes) que luego transcribes a una tabla?
- ¿Qué campos concretos te gustaría separar de ese texto (nombre, monto, fecha)?

### Herramientas

- [ ] **Tu escenario de Make** con Gemini (Sesión 3).
- [ ] **Gmail** — para enviarte correos de prueba de "ventas".
- [ ] **Un Google Sheet** con una pestaña `Ventas` (la crearás en clase si no la tienes).

### Lectura sugerida

- [¿Qué es JSON? (explicado simple)](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/JSON){:target="_blank"} — Introducción amable.
- [Parse JSON en Make](https://www.make.com/en/help/tools/json){:target="_blank"} — Documentación del módulo y los Data Structures.

---

## Glosario

| Término | Definición |
|---------|------------|
| **JSON** | Formato estándar de datos: objetos `{}`, arrays `[]`, pares clave-valor. |
| **System prompt** | Instrucción que fija cómo debe responder la IA (ej: "responde SOLO en JSON"). |
| **Data Structure** | El "molde" en Make que describe nombres y tipos de cada campo del JSON. |
| **Parse JSON** | Módulo de Make que convierte el texto JSON en variables usables. |
| **Variable** | Cada campo resultante (vendedor, monto...) que arrastras a un módulo siguiente. |

---

## Recursos Adicionales

- [Pedir salida estructurada a Gemini](https://ai.google.dev/gemini-api/docs/structured-output){:target="_blank"} — Cómo forzar respuestas JSON.
- [Data Structures en Make](https://www.make.com/en/help/tools/data-structures){:target="_blank"} — Crear y editar moldes.
