# Test Módulo 1 - Questions

**5 preguntas diagnósticas** | **Duración:** 10 min | **No afecta calificación**

---

## Pregunta 1 (Clase 01 — Prompts y Gems)

Un colega te dice: "Le pregunté a Gemini lo mismo 3 veces en chats distintos y siempre tengo que repetirle quién soy y qué hago. Es agotador." ¿Qué le falta a su flujo?

A. Usar un modelo pago de Gemini
B. Configurar un Gem con instrucciones y archivos de referencia persistentes
C. Aplicar la estructura Rol + Contexto + Tarea + Formato + Restricciones
D. Pasar a un servicio diferente (Claude o ChatGPT)

> **Respuesta:** B. Un Gem persiste contexto fijo (instrucciones + archivos) — eliminás la repetición. Las opciones A y D no atacan el problema; la C ayuda en cada prompt individual pero no resuelve la repetición.

---

## Pregunta 2 (Clase 02 — Google Sheets con IA)

Estás diseñando el Sheet de tu sistema. La meta semanal del negocio (S/ 20,000) y los nombres de los 3 vendedores aparecen en muchos cálculos. ¿Cuál es la decisión correcta de diseño?

A. Repetir esos valores en una columna de la pestaña operativa para que estén disponibles fila por fila
B. Guardarlos en una pestaña `Config` y referenciarlos vía rangos nombrados desde donde haga falta
C. Hardcodearlos en las fórmulas de Make para que sean inmutables
D. Crear un archivo separado de Drive solo para parámetros

> **Respuesta:** B. La separación operativa/Config + rangos nombrados es el corazón del Módulo 1. Cambiar la meta una vez actualiza todo el sistema. Sin esa separación, tocás 50 filas (A) o tenés que editar Make cada vez (C).

---

## Pregunta 3 (Clase 03 — Marcadores variables)

Tu plantilla de Slides tiene estos 3 marcadores: `{{ventas_total}}`, `{{variacion_pct}}` y `{{hallazgo_1}}`. Para conectar el sistema en la Clase 4 y 5, necesitás saber el origen de cada uno. ¿Qué tipos son, en orden?

A. Crudo · Crudo · Calculado
B. Crudo · Calculado · Generado por IA
C. Calculado · Calculado · Generado por IA
D. Generado por IA · Crudo · Calculado

> **Respuesta:** B. `ventas_total` viene directo de una celda del Sheet (crudo). `variacion_pct` requiere fórmula sobre 2 valores (calculado por Make). `hallazgo_1` es un insight contextual (generado por Gemini).

---

## Pregunta 4 (Clase 04 — Make básico sin IA)

Tu escenario semanal en Make tiene: Search Rows (1) + Create from Template (1) + 10 Replace Text (10) + Export PDF (1) + Send Email (1). Para procesar correos en vivo durante el día, además necesitás un segundo escenario. ¿Qué configuración usás y por qué?

A. El mismo escenario semanal con trigger Scheduled cada 5 minutos — total ~14 ops por corrida
B. Un escenario separado con Instant Trigger de Gmail — reacciona en 2-5 segundos y consume ops solo cuando llega correo
C. Un escenario separado con Scheduled cada hora — minimiza el consumo de operaciones
D. El mismo escenario semanal pero corriendo manualmente cada vez que llega un correo

> **Respuesta:** B. Instant es la única opción que reacciona en segundos sin desperdiciar operaciones. La C consume ops cada hora aunque no haya correos; la A duplica trabajo y revienta el plan free; la D no escala.

---

## Pregunta 5 (Integración M1)

Llegás a la Clase 5 con: Gem configurado, Sheet con 3 pestañas y rangos nombrados, plantilla de Slides con 18 marcadores. PERO no actualizaste la tabla de parámetros desde la Clase 2. ¿Qué problema específico vas a tener al armar los prompts de Gemini API?

A. Ninguno — la tabla de parámetros es solo organización personal
B. Make no podrá leer el Sheet sin la tabla
C. Tendrás que abrir Sheet, Slides y notas mentales para rastrear de dónde viene cada marcador en cada prompt — lento y propenso a errores
D. Los marcadores tipo IA no podrán generarse

> **Respuesta:** C. La tabla de parámetros es el mapa unificado del sistema. Sin ella, cada prompt de IA requiere rastrear el origen del marcador manualmente. El sistema sigue funcionando técnicamente, pero la productividad cae 3-5x.

---

## Clave de Respuestas Rápida

| # | Respuesta | Clase | Tema |
|---|-----------|-------|------|
| 1 | B | C01 | Gems como contexto persistente |
| 2 | B | C02 | Arquitectura Config + rangos nombrados |
| 3 | B | C03 | Clasificación de marcadores (crudo/calculado/IA) |
| 4 | B | C04 | Instant vs Scheduled + consumo de operaciones |
| 5 | C | Integración | Tabla de parámetros como mapa del sistema |

---

## Análisis para el instructor

Si hay **<60% de acierto** en alguna pregunta, retomar el concepto al inicio de la Clase 5 antes de avanzar:

- **Pregunta 1 (Gems):** demo rápida del Gem en vivo + revisar instrucciones de uno de los estudiantes en pantalla
- **Pregunta 2 (Sheets):** ejercicio de "¿operativa o Config?" con 5 ejemplos en chat
- **Pregunta 3 (Marcadores):** clasificar 5 marcadores en vivo con el grupo antes de armar prompts JSON
- **Pregunta 4 (Make):** revisar 1 historial de ejecución del escenario instantáneo en pantalla — el "efecto WOW" en vivo refuerza el concepto
- **Pregunta 5 (Integración):** dedicar 10 min al inicio de Clase 5 a completar/actualizar la tabla de parámetros con el grupo

**Si el promedio del grupo es <70%:** considerar reorganizar la Clase 5 para empezar con un repaso integrador de M1 (15-20 min) antes de introducir Gemini API.

**Si el promedio es >85%:** el grupo está sólido — avanzar directo con la API y aprovechar el tiempo extra para profundizar en optimización de prompts (anticipo de C06).
