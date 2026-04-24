# Test Módulo 2 - Questions

**8 preguntas diagnósticas** | **Duración:** 15 min | **No afecta calificación**

---

## Pregunta 1 (Clase 05 — Gemini API)

¿Dónde va la API key de Gemini en una llamada HTTP desde Make?

A. En los headers como `Authorization: Bearer YOUR_KEY`
B. En el body JSON como `"api_key": "YOUR_KEY"`
C. Al final de la URL como `?key=YOUR_KEY`
D. En una variable de entorno separada

> **Respuesta:** C. Gemini API usa el formato `?key=YOUR_KEY` al final de la URL del endpoint.

---

## Pregunta 2 (Clase 05 — JSON)

El módulo Parse JSON de Make falla con error "Invalid JSON". ¿Cuál es la causa MÁS probable?

A. La API key de Gemini caducó
B. Gemini respondió con texto introductorio antes del JSON (ej: "Aquí está tu respuesta:")
C. El prompt era demasiado largo
D. La cuota diaria de 1,500 requests se agotó

> **Respuesta:** B. Parse JSON es literal — si hay cualquier texto que no sea JSON puro al inicio, falla. Solución: agregar al prompt "responde SOLO JSON, sin markdown ni texto adicional".

---

## Pregunta 3 (Clase 06 — Prompt engineering)

De estas 3 técnicas, ¿cuál aporta MÁS a reducir inconsistencia en la salida de Gemini?

A. Chain of thought ("piensa paso a paso")
B. Persona explícita ("eres analista senior")
C. Few-shot (incluir 2 ejemplos de output deseado)
D. Aumentar longitud del prompt general

> **Respuesta:** C. Few-shot es la técnica más efectiva para consistencia — muestra a la IA exactamente qué tipo de output querés.

---

## Pregunta 4 (Clase 06 — Mejores prácticas)

Configuraste un error handler en modo "Resume" en el módulo HTTP a Gemini. ¿Qué pasa si ese módulo falla una vez?

A. El escenario completo se detiene y se envía alerta
B. El módulo se reintenta infinitamente hasta funcionar
C. El escenario continúa con los módulos siguientes; el error handler ejecuta en paralelo
D. Solo se envía la alerta, no se genera el reporte esa semana

> **Respuesta:** C. "Resume" permite continuar después del error. El error handler envía la alerta, y el flujo sigue con los módulos posteriores.

---

## Pregunta 5 (Clase 07 — Transferencia)

Duplicás un escenario de Make vía Export/Import Blueprint. Después de importar, ¿qué debe reconfigurarse ANTES de activar el escenario v2?

A. Solo las conexiones a Sheet/Slides (apuntan a recursos nuevos)
B. Solo los SystemPrompts (para adaptar a tu caso)
C. Las conexiones Y los SystemPrompts
D. Nada — el blueprint preserva todo automáticamente

> **Respuesta:** C. El blueprint preserva la estructura, pero los recursos apuntan a los originales y hay que redireccionarlos. Además, el SystemPrompt del HTTP menciona el caso original.

---

## Pregunta 6 (Clase 07 — Personalización)

Los 5 puntos críticos de personalización al transferir el sistema al caso propio son:

A. Datos + Sheet + Slides + Prompts + Destinatarios/frecuencia
B. Marca + Colores + Tipografía + Logo + Paleta
C. Gmail + Drive + Calendar + Meet + Chat
D. Semana 1 + Semana 2 + Semana 3 + Semana 4 + Ajustes

> **Respuesta:** A. Los 5 puntos son los elementos que cambian según el caso.

---

## Pregunta 7 (Clase 08 — ROI)

Un estudiante ahorra 5 horas/semana con su sistema. Su tarifa efectiva es S/ 40/hora. ¿Cuál es su ROI ANUAL?

A. S/ 200
B. S/ 800
C. S/ 9,600
D. S/ 19,200

> **Respuesta:** C. Fórmula: 5 h/sem × S/ 40/h × 4 sem = S/ 800/mes. S/ 800 × 12 = S/ 9,600/año.

---

## Pregunta 8 (Integración M1+M2)

Un estudiante completó las 8 sesiones. Su sistema está activo con:
- Escenario 1 Instant (Gmail → Gemini → Sheet)
- Escenario 2 Scheduled (Sheet → Gemini → Slides → PDF → Gmail + Historico)

¿Cuántas operaciones de Make consume APROXIMADAMENTE por cada reporte semanal generado?

A. 5 operaciones
B. 15 operaciones
C. 30 operaciones
D. 100 operaciones

> **Respuesta:** C. El Escenario 2 típico con IA: Scheduled (1) + Search Rows (1) + HTTP Gemini (1) + Parse JSON (1) + Create Template (1) + 10-15 Replace Text (10-15) + Export PDF (1) + Send Email (1) + Add row Historico (1) + Upload Backup (1) = ~28-30 ops.

---

## Clave de Respuestas Rápida

| # | Respuesta | Tema |
|---|-----------|------|
| 1 | C | API key en URL |
| 2 | B | Parse JSON falla por texto extra |
| 3 | C | Few-shot reduce inconsistencia |
| 4 | C | Error handler Resume |
| 5 | C | Reconfiguración tras clonar |
| 6 | A | 5 puntos de personalización |
| 7 | C | Cálculo de ROI anual |
| 8 | C | Operaciones por reporte |

---

## Análisis para el instructor

Si hay <60% de acierto en:

- **Pregunta 1:** muchos estudiantes tienen mala configuración — sospechar sistemas que no funcionan en Demo Day
- **Pregunta 2:** sistemas con Parse JSON failing; recomendar revisión de prompts post-curso
- **Pregunta 3:** grupo no internalizó few-shot; recomendar práctica en plan 30 días
- **Pregunta 4:** mejores prácticas no aplicadas; riesgo de sistemas que fallan silenciosamente
- **Pregunta 5:** algunos no entienden la clonación; revisar sus sistemas v2 antes de demos
- **Pregunta 6:** plan de personalización fue superficial; candidatos a mentoría post-curso
- **Pregunta 7:** problema de matemáticas básicas; validar cálculos de ROI uno por uno
- **Pregunta 8:** no entienden consumo de ops; riesgo de agotar plan free pronto
