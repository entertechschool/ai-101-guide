# Test Módulo 2 - Questions

**5 preguntas diagnósticas** | **Duración:** 10 min | **No afecta calificación**

---

## Pregunta 1 (Clase 05 — Gemini API + JSON)

Configurás un módulo HTTP en Make para llamar a Gemini API. La llamada funciona pero el siguiente módulo Parse JSON falla con error "Invalid JSON". Revisás la respuesta y ves que empieza con: `Claro, aquí está tu JSON: {...}`. ¿Cuáles son los DOS arreglos que necesita la configuración?

A. Mover la API key del header al cuerpo + cambiar el modelo a Gemini Pro
B. Poner la API key como `?key=YOUR_KEY` al final de la URL + agregar al prompt "responde SOLO JSON, sin markdown ni texto adicional"
C. Aumentar el timeout del módulo HTTP + reducir el tamaño del prompt
D. Cambiar el método HTTP de POST a GET + reformatear el JSON

> **Respuesta:** B. Son los 2 fundamentos de Clase 5: la key va al final de la URL (no en headers tipo Bearer como otras APIs), y el prompt debe ser estricto para que Parse JSON no falle ante texto introductorio. Las otras opciones no atacan los problemas reales.

---

## Pregunta 2 (Clase 06 — Optimización + mejores prácticas)

Tu sistema modelo en producción tiene insights "planos" ("las ventas subieron") y a veces falla silenciosamente cuando Gemini API se cae. ¿Cuál combinación de cambios resuelve AMBOS problemas a la vez?

A. Cambiar al modelo Gemini Pro + aumentar el timeout del HTTP
B. Reescribir el prompt con persona + few-shot + chain of thought, y agregar un error handler en modo "Resume" con alerta por correo
C. Ejecutar el escenario más seguido para tener más datos
D. Renombrar los marcadores con snake_case más descriptivo

> **Respuesta:** B. Few-shot transforma insights planos en accionables (storytelling: dato + comparación + causa + acción). El error handler "Resume" deja que el flujo continúe y manda alerta — sin él, los fallos pasan inadvertidos. Las opciones A, C, D no atacan los 2 problemas mencionados.

---

## Pregunta 3 (Clase 07 — Transferencia y personalización)

Duplicás un escenario de Make vía Export/Import Blueprint para tu caso real. Lo activás sin cambiar nada y notás que: (1) escribe en el Sheet de Roberto en vez del tuyo, y (2) Gemini genera insights de ventas aunque tu caso es marketing. ¿Cuáles son los 2 ajustes mínimos para tu caso propio?

A. Reconectar las conexiones a tu Sheet/Slides v2 + reescribir el SystemPrompt del HTTP con tu industria y contexto
B. Solo cambiar las credenciales de Make a tu cuenta personal
C. Cambiar el nombre del escenario y la zona horaria
D. Pagar el plan de Make Pro para evitar conflictos entre escenarios

> **Respuesta:** A. El Blueprint preserva la estructura del flujo, pero los recursos apuntan al original (problema 1) y los prompts mencionan el caso modelo (problema 2). Adaptar conexiones y prompts es el mínimo. Esto se conecta con los 5 puntos de personalización (datos, Sheet, Slides, prompts, destinatarios).

---

## Pregunta 4 (Clase 08 — ROI)

Trabajás 160 horas al mes y ganás S/ 4,000 netos mensuales. Tu sistema te ahorra 5 horas a la semana. ¿Cuál es tu ROI ANUAL aplicando la fórmula del curso?

A. S/ 800
B. S/ 6,000
C. S/ 9,600
D. S/ 25,000

> **Respuesta:** B. Tarifa efectiva: 4,000 ÷ 160 = S/ 25/hora. Ahorro mensual: 5 × 25 × 4 = S/ 500/mes. Ahorro anual: 500 × 12 = **S/ 6,000/año**. La A es solo mensual ×1.6; la C usa S/ 40/hora (no la calculada); la D infla la tarifa.

---

## Pregunta 5 (Integración M1+M2)

Tu sistema completo está activo: Escenario 1 Instant (Gmail → Gemini → Sheet) consume ~4 ops por correo capturado, y Escenario 2 Scheduled (Sheet → Gemini → Slides → PDF → Gmail + Historico) consume ~28 ops por reporte semanal. Si capturás 50 correos por mes y emitís 4 reportes mensuales, ¿llegás al límite de 1,000 ops/mes del plan free?

A. Sí, te quedás sin operaciones la segunda semana del mes
B. Justo en el límite (~1,000 ops); cualquier corrida extra agota el plan
C. No — consumís ~312 ops, queda margen amplio para crecer
D. Imposible saberlo sin medir el consumo real durante un mes

> **Respuesta:** C. Cálculo: (50 correos × 4 ops) + (4 reportes × 28 ops) = 200 + 112 = **312 ops/mes**. Te queda ~70% del plan libre para ajustes, errores o agregar agentes nuevos del plan 30 días. Esto valida que el plan free es suficiente para uso profesional real.

---

## Clave de Respuestas Rápida

| # | Respuesta | Clase | Tema |
|---|-----------|-------|------|
| 1 | B | C05 | Gemini API + JSON estricto |
| 2 | B | C06 | Optimización de prompts + error handlers |
| 3 | A | C07 | Transferencia: conexiones + SystemPrompt |
| 4 | B | C08 | Cálculo de ROI con tarifa efectiva |
| 5 | C | Integración | Consumo total del sistema vs plan free |

---

## Análisis para el instructor

Si hay **<60% de acierto** en alguna pregunta, indica un riesgo concreto post-curso:

- **Pregunta 1 (API + JSON):** estudiantes con sistemas que probablemente no funcionan o fallan intermitentemente. Riesgo en Demo Day. Hacer revisión 1 a 1 de las llamadas HTTP antes de presentar.
- **Pregunta 2 (Optimización + error handlers):** sistemas que generan insights tibios y/o fallan silenciosamente en producción. Riesgo de abandono post-curso porque el sistema "no parece útil". Recomendar plan 30 días que incluya 1 ronda de optimización de prompts.
- **Pregunta 3 (Transferencia):** los estudiantes no internalizaron qué cambia y qué se queda. Riesgo de no poder construir los 3 agentes del plan 30 días. Revisar sistemas v2 antes de Demo Day.
- **Pregunta 4 (ROI):** error de cálculo o de aplicación de la fórmula. Validar el ROI de cada estudiante en vivo antes de Demo Day — un ROI bien calculado es el argumento principal para justificar el curso a su jefe/empresa.
- **Pregunta 5 (Consumo):** estudiantes no internalizan que el plan free es suficiente. Riesgo de pagar Make Pro innecesariamente o de abandonar pensando "mi sistema se rompió". Reforzar con la pestaña Logs durante Demo Day.

**Si el promedio del grupo es <70%:** considerar agregar una sesión post-curso opcional de 1h para revisar sistemas en producción y hacer ajustes antes de la primera semana del plan 30 días.

**Si el promedio es >85%:** grupo listo para AI 201. Mencionarlo explícitamente en el cierre del Demo Day como invitación.
