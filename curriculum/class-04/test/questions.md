# Test diagnóstico Sesiones 1-4 - Questions

**5 preguntas diagnósticas** | **Duración:** 10 min | **No afecta calificación**

---

## Pregunta 1 (Sesión 01 — Prompts efectivos)

Un colega le pide a Gemini "escribe sobre productividad" y recibe una respuesta genérica que no puede usar. ¿Qué le falta a su prompt para volverlo profesional?

A. Un modelo pago de Gemini
B. Aplicar la anatomía: rol + tarea + contexto + formato
C. Repetir la misma pregunta varias veces hasta que mejore
D. Escribir el prompt en inglés

> **Respuesta:** B. La anatomía rol + tarea + contexto + formato es lo que ancla la respuesta a su caso. El modelo (A) y el idioma (D) no atacan el problema; repetir (C) no agrega información.

---

## Pregunta 2 (Sesión 02 — Make 101 + Google Cloud)

Al conectar Make con tu cuenta de Google vía OAuth, ¿qué es lo que Make recibe y usa para acceder a tu Drive?

A. Tu contraseña de Google, que queda guardada en Make
B. Un token que Google emite tras aprobar permisos — tu contraseña nunca se comparte
C. El Client Secret, que reemplaza a tu contraseña
D. Un código de un solo uso que caduca en 5 minutos

> **Respuesta:** B. OAuth funciona con un token que Google entrega tras tu aprobación; la contraseña nunca viaja a Make. El Client ID/Secret identifican la app, pero el acceso se da por el token.

---

## Pregunta 3 (Sesión 03 — API key de Gemini)

Vas a usar Gemini en varios escenarios de Make para leer facturas simples y de alto volumen. ¿Qué decisiones son las correctas?

A. Pegar la API key en cada módulo y usar Gemini Pro
B. Guardar la key como Connection reutilizable y usar Gemini Flash
C. Guardar la key como Connection y usar Gemini Pro para todo
D. Pegar la key en cada módulo y usar Gemini Flash

> **Respuesta:** B. La Connection guarda la credencial de forma segura y reutilizable; Flash es rápido y económico, ideal para tareas simples de alto volumen. Pro (A, C) es innecesario y caro aquí; pegar la key suelta (A, D) la expone.

---

## Pregunta 4 (Sesión 04 — JSON + Parse JSON)

Le pides a Gemini que extraiga datos de un correo y quieres que cada dato caiga en su columna del Sheet. ¿Qué combinación lo logra de forma confiable?

A. Pedir la respuesta en texto libre y separar los datos a mano
B. Pedir la respuesta en JSON + un Data Structure + módulo Parse JSON
C. Pedir la respuesta en JSON y mapearla directo sin Parse JSON
D. Usar Gemini Pro para que el texto salga mejor ordenado

> **Respuesta:** B. El JSON da estructura, el Data Structure define el molde y Parse JSON lo convierte en variables. Sin Parse (C) la salida es un solo bloque de texto; el texto libre (A) es frágil; el modelo (D) no resuelve el mapeo.

---

## Pregunta 5 (Integración — el flujo de facturas)

En el sistema de facturas que construyes, ¿cuál es el orden correcto de los módulos para que una factura nueva termine registrada con sus datos separados?

A. Sheets Add a Row → Drive Watch → Gemini → Parse JSON
B. Drive Watch Files → Gemini (JSON) → Parse JSON → Sheets Add a Row
C. Gemini → Drive Watch Files → Sheets Add a Row → Parse JSON
D. Drive Watch Files → Sheets Add a Row → Gemini → Parse JSON

> **Respuesta:** B. Primero el trigger (entra la factura), luego Gemini la lee y devuelve JSON, Parse JSON lo separa en variables y recién al final se escribe la fila en el Sheet. Cualquier otro orden rompe el flujo de datos.

---

## Clave de Respuestas Rápida

| # | Respuesta | Sesión | Tema |
|---|-----------|--------|------|
| 1 | B | S01 | Anatomía del prompt |
| 2 | B | S02 | OAuth (token, no contraseña) |
| 3 | B | S03 | Connection + Flash |
| 4 | B | S04 | JSON + Data Structure + Parse |
| 5 | B | Integración | Orden del flujo de facturas |

---

## Análisis para el instructor

Si hay **<60% de acierto** en alguna pregunta, retomar el concepto al inicio de la siguiente sesión:

- **Pregunta 1 (Prompts):** mejorar un prompt débil en vivo, agregando rol/contexto/formato.
- **Pregunta 2 (OAuth):** repasar los 5 pasos de OAuth con la analogía de la llave de hotel.
- **Pregunta 3 (API key):** mostrar la diferencia entre Connection y key suelta en Make.
- **Pregunta 4 (JSON):** parsear una respuesta de Gemini en vivo con "Generate from sample".
- **Pregunta 5 (Flujo):** dibujar el flujo de facturas de punta a punta en pantalla.

**Si el promedio del grupo es <70%:** dedicar 15 min a un repaso integrador antes de avanzar a plantillas.

**Si el promedio es >85%:** el grupo está sólido — avanzar directo a plantillas con placeholders.
