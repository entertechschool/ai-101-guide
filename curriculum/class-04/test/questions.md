# Test Módulo 1 - Questions

**8 preguntas diagnósticas** | **Duración:** 15 min | **No afecta calificación**

---

## Pregunta 1 (Clase 01 — Prompts)

Un prompt profesional bien estructurado incluye 5 elementos. ¿Cuál de los siguientes NO es uno de los 5?

A. Rol
B. Contexto
C. Temperature
D. Restricciones

> **Respuesta:** C. Temperature es un parámetro técnico de la API (lo verás en Clase 5), no parte de la estructura del prompt profesional.

---

## Pregunta 2 (Clase 01 — Gems)

¿Cuál es la ventaja principal de usar un Gem personalizado en vez del chat normal de Gemini?

A. Los Gems tienen modelos más potentes que el chat normal
B. Los Gems mantienen contexto fijo (instrucciones y archivos) sin repetirlo cada vez
C. Los Gems no consumen tokens del plan gratuito
D. Los Gems procesan más rápido las respuestas

> **Respuesta:** B. Los Gems persisten las instrucciones y archivos de referencia — dejas de pegar el mismo contexto en cada conversación.

---

## Pregunta 3 (Clase 02 — 3 pestañas)

¿Por qué conviene separar los parámetros del negocio (meta, vendedores) en una pestaña `Config` distinta a la pestaña operativa?

A. Porque Make lee más rápido cuando las pestañas están separadas
B. Porque evita tener que editar la misma columna en 50 filas cuando cambia un parámetro
C. Porque los gráficos solo funcionan con datos de Config
D. Porque Gemini no puede leer pestañas mixtas

> **Respuesta:** B. Un parámetro vive en una sola celda de Config — cambiarlo una vez actualiza todo. Sin esa separación, tocarías 50 filas.

---

## Pregunta 4 (Clase 02 — Rangos nombrados)

¿Cuál es el beneficio principal de usar un rango nombrado (`RangoVentas`) en Make en vez de coordenadas (`A1:G50`)?

A. Los rangos nombrados son más rápidos de leer
B. Make solo soporta rangos nombrados
C. El flujo no se rompe si alguien agrega o reordena columnas del Sheet
D. Los rangos nombrados consumen menos operaciones de Make

> **Respuesta:** C. Robustez ante cambios. Si un compañero agrega una columna, `A:G` sigue leyendo G (perdiste info); `RangoVentas` se ajusta.

---

## Pregunta 5 (Clase 03 — Tipos de marcadores)

El marcador `{{variacion_pct}}` que compara ventas de esta semana con la anterior, ¿de qué tipo es?

A. Crudo (viene directo del Sheet)
B. Calculado (Make lo calcula con módulo Math)
C. Generado por IA (Gemini lo produce)
D. Manual (se llena a mano antes de correr el flujo)

> **Respuesta:** B. Hay 2 valores (ventas actual y anterior) y se calcula la variación — eso es tipo 2, calculado por Make.

---

## Pregunta 6 (Clase 04 — Instant vs Scheduled)

Para un sistema que recibe correos de ventas durante el día y debe actualizar el Sheet lo más rápido posible, ¿qué trigger es el correcto?

A. Scheduled cada 1 hora
B. Scheduled cada 5 minutos
C. Instant Trigger
D. Manual (Run once cada vez)

> **Respuesta:** C. Instant reacciona en 2-5 segundos vs 1 hora o 5 min. Además consume ops solo cuando hay correo, no en cada revisión vacía.

---

## Pregunta 7 (Clase 04 — Operaciones)

Tu escenario semanal usa: Search Rows (1), Create from Template (1), 10 Replace Text (10), Export PDF (1), Send Email (1). ¿Cuántas operaciones consume por reporte?

A. 5
B. 12
C. 14
D. 50

> **Respuesta:** C. 1+1+10+1+1 = 14 ops por reporte. Con 1,000 ops/mes, eso son ~71 reportes máximos.

---

## Pregunta 8 (Integración M1)

Un estudiante llega a la Clase 5 con Gem configurado, Sheet con 3 pestañas y rangos nombrados, plantilla de Slides con 18 marcadores, pero SIN tabla de parámetros actualizada. ¿Qué problema específico va a tener?

A. Ninguno, la tabla es opcional
B. No podrá conectar Gemini API en Make
C. Tendrá que abrir 3 archivos distintos cada vez que quiera saber de dónde viene cada marcador
D. Su plantilla de Slides no funcionará con Replace Text

> **Respuesta:** C. La tabla de parámetros es el mapa unificado. Sin ella, cada vez que configuras un prompt para un marcador tipo IA, tenés que rastrear manualmente de qué celda del Sheet viene. Es lento y propenso a errores.

---

## Clave de Respuestas Rápida

| # | Respuesta | Tema |
|---|-----------|------|
| 1 | C | Estructura de prompt profesional |
| 2 | B | Gems y contexto persistente |
| 3 | B | Separación Config/Operativa |
| 4 | C | Rangos nombrados |
| 5 | B | Clasificación de marcadores |
| 6 | C | Instant Trigger |
| 7 | C | Conteo de operaciones |
| 8 | C | Tabla de parámetros |

---

## Análisis para el instructor

Si hay <60% de acierto en:

- **Pregunta 1:** repasar anatomía del prompt en apertura de Clase 5
- **Pregunta 2:** demo rápida del Gem en vivo al inicio de Clase 5
- **Preguntas 3-4:** revisar estructura del Sheet antes de integrar Gemini API
- **Pregunta 5:** retomar antes de que armen prompts tipo IA
- **Preguntas 6-7:** consolidar conceptos de Make en pausa de Clase 5
- **Pregunta 8:** hacer ejercicio rápido de completar tabla de parámetros en grupo
