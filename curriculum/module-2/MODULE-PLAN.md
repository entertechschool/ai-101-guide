# Plan del Módulo 2: Integración y Proyecto

> Documento de arquitectura del módulo. Alineado al sílabo v3 y a las clases ya generadas.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | 2 |
| **Título** | Integración y Proyecto |
| **Tema Central** | Convertir datos en documentos, robustecer el flujo y llevar el método al caso propio |
| **Sesiones** | 5 a 8 |
| **Duración por sesión** | 60 min (Apertura 10 · Fundamentos 20 · Mini-proyecto 25 · Cierre 5) |
| **Pre-requisitos** | Módulo 1 completo (prompts, Make + Cloud, Gemini, JSON/Parse) |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **Generar documentos y presentaciones** automáticas con plantillas y placeholders `{{variable}}`.
2. **Diseñar un flujo end-to-end robusto** (Watch vs Schedule, filtros, routers, manejo de errores, logs).
3. **Construir un proyecto integrador propio** para un caso real de su trabajo.
4. **Sustentar el proyecto** en Demo Day (caso → demo → resultados → aprendizajes).

---

## Caso guía y evaluación

- **Caso guía (S5-6):** el sistema de facturas se completa (reporte mensual + flujo robusto). **Caso propio (S7-8):** el estudiante lo lleva a su trabajo.
- **Evaluación:** práctica en clase **0/100** por sesión. Proyecto integrador (S7) + Demo Day (S8). Sin entregables post-clase.
- **Test diagnóstico:** al inicio de la Sesión 8 (control interno, no califica).

---

## Evolución por Sesión

| Sesión | Enfoque | Resultado al finalizar |
|--------|---------|------------------------|
| 5 | Plantillas con placeholders | Reporte mensual de facturas generado desde el Sheet |
| 6 | Flujo end-to-end robusto | Flujo completo con filtros, router y manejo de errores |
| 7 | Proyecto integrador | v1 del flujo propio del estudiante con datos reales |
| 8 | Exposición / Demo Day | Proyecto sustentado + roadmap personal |

---

## Arquitectura de Sesiones

### Sesión 5 — Plantillas con placeholders
- **Concepto:** plantilla, placeholders `{{variable}}`, mapeo dato→placeholder, Create from Template (Slides/Docs), formato de datos.
- **Mini-proyecto:** reporte mensual de facturas (Sheet → Slide con plantilla).
- **Herramienta nueva:** Google Slides/Docs (plantillas) en Make.

### Sesión 6 — Flujo end-to-end robusto
- **Concepto:** Watch vs Schedule, filtros y routers, manejo de errores/notificaciones, logs y depuración.
- **Mini-proyecto:** flujo completo de facturas (Drive → IA → Sheets → Docs → Email) con filtros, router y error handler.
- **Herramientas nuevas:** filtros, routers, error handler.

### Sesión 7 — Proyecto integrador
- **Concepto:** estructura del proyecto (problema → solución → arquitectura), diagramar antes de construir, iteración.
- **Mini-proyecto:** v1 del flujo propio con datos reales (acompañamiento 1 a 1).
- **Herramientas nuevas:** ninguna (se aplica todo el stack).

### Sesión 8 — Exposición / Demo Day (cierre)
- **Concepto:** estructura de la expo (caso → demo → resultados → aprendizajes), preparar la demo, comunicar resultados (cuanti + cuali).
- **Mini-proyecto:** Demo Day — presentación de 5 min + Q&A + feedback + roadmap personal.
- **Test diagnóstico:** 5 preguntas (Sesiones 5-8).

---

## Cierre del curso

Al terminar el Módulo 2, el estudiante tiene:
- Un flujo automatizado propio funcionando con datos reales.
- Un resultado tangible comunicable (tiempo ahorrado, costo, items procesados).
- Un roadmap personal con sus próximas automatizaciones.
