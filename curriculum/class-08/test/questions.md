# Test diagnóstico Sesiones 5-8 - Questions

**5 preguntas diagnósticas** | **Duración:** 10 min | **No afecta calificación**

---

## Pregunta 1 (Sesión 05 — Plantillas con placeholders)

En tu plantilla de Slides escribiste `{{Total}}` pero en el mapeo de Make la variable se llama `total`. Corres el flujo y el documento sale con el texto `{{Total}}` literal, sin reemplazar. ¿Por qué?

A. Make no soporta placeholders en Slides, solo en Docs
B. El nombre del placeholder y el del mapeo deben coincidir exacto (la mayúscula los hace distintos)
C. Falta convertir el número con formatNumber
D. La plantilla no estaba compartida con Make

> **Respuesta:** B. Create from Template / Replace Text buscan coincidencia literal: `{{Total}}` ≠ `{{total}}`. Una mayúscula o un espacio de más dejan el marcador sin reemplazar.

---

## Pregunta 2 (Sesión 06 — Flujo end-to-end robusto)

Tu flujo de facturas a veces procesa archivos que no son facturas (gasta IA en vano) y, cuando Gemini se cae, nadie se entera. ¿Qué combinación resuelve AMBOS problemas?

A. Cambiar el trigger de Watch a Schedule
B. Agregar un filtro (solo PDF/factura) antes de la IA + un error handler "Resume" con alerta por correo
C. Usar Gemini Pro en vez de Flash
D. Aumentar el intervalo de chequeo del trigger

> **Respuesta:** B. El filtro evita procesar lo que no corresponde (ahorra IA y operaciones); el error handler "Resume" deja seguir el flujo y avisa cuando algo falla. Las demás opciones no atacan ninguno de los dos problemas.

---

## Pregunta 3 (Sesión 07 — Proyecto integrador)

Vas a construir tu propio flujo para un caso real. ¿Cuál es el primer paso recomendado antes de abrir Make?

A. Activar un escenario y probar a ver qué pasa
B. Diagramar el flujo en una hoja: trigger → módulos → output
C. Comprar el plan Pro de Make para tener más operaciones
D. Escribir todos los prompts finales optimizados

> **Respuesta:** B. Diagramar primero (problema → solución → arquitectura) ahorra horas de módulos mal conectados. Construir sin plan (A) o cerrar detalles finos antes de la v1 (D) es ineficiente; el plan Pro (C) es innecesario.

---

## Pregunta 4 (Sesión 08 — Exposición / Demo Day)

Tienes 5 minutos para sustentar tu proyecto. ¿Cuál es la estructura recomendada y qué es lo más importante?

A. Solo slides explicando la arquitectura técnica en detalle
B. Caso → demo en vivo → resultados → aprendizajes, donde la demo en vivo es el centro
C. Leer el código módulo por módulo
D. Mostrar el ROI calculado en una hoja de cálculo durante los 5 minutos

> **Respuesta:** B. La estructura es caso → demo → resultados → aprendizajes, y la demo en vivo (el sistema funcionando) es lo que más impacta. Una demo clara vale más que mil slides.

---

## Pregunta 5 (Integración — el flujo completo)

Tu sistema de facturas activo consume ~4 ops por archivo y ~28 ops por reporte mensual. Si procesas 50 facturas y emites 4 reportes al mes, ¿llegas al límite de 1,000 ops/mes del plan free de Make?

A. Sí, te quedas sin operaciones la segunda semana
B. Justo en el límite (~1,000 ops)
C. No — consumes ~312 ops, queda margen amplio
D. Imposible saberlo sin medir un mes real

> **Respuesta:** C. (50 × 4) + (4 × 28) = 200 + 112 = **312 ops/mes**. Queda ~70% del plan libre. El plan gratuito alcanza de sobra para uso profesional real.

---

## Clave de Respuestas Rápida

| # | Respuesta | Sesión | Tema |
|---|-----------|--------|------|
| 1 | B | S05 | Placeholders: nombre exacto |
| 2 | B | S06 | Filtro + error handler |
| 3 | B | S07 | Diagramar antes de construir |
| 4 | B | S08 | Estructura de la expo + demo en vivo |
| 5 | C | Integración | Consumo del flujo vs plan free |

---

## Análisis para el instructor

Si hay **<60% de acierto** en alguna pregunta, refuerza el concepto:

- **Pregunta 1 (Placeholders):** mostrar en vivo un marcador que no coincide y cómo arreglarlo.
- **Pregunta 2 (Flujo robusto):** revisar un filtro y un error handler en un escenario real.
- **Pregunta 3 (Diagramar):** dibujar juntos un flujo antes de construirlo.
- **Pregunta 4 (Expo):** repasar la estructura caso → demo → resultados → aprendizajes.
- **Pregunta 5 (Consumo):** revisar el History y el contador de operaciones de Make.

**Si el promedio del grupo es >85%:** grupo listo para AI 201 — mencionarlo en el cierre.
