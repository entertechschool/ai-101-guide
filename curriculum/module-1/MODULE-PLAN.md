# Plan del Módulo 1: Fundamentos del Sistema

> Documento de arquitectura del módulo. Alineado al sílabo v3 y a las clases ya generadas.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | 1 |
| **Título** | Fundamentos del Sistema |
| **Tema Central** | Construir, pieza por pieza, las bases del sistema sobre el caso guía de facturas |
| **Sesiones** | 1 a 4 |
| **Duración por sesión** | 60 min (Apertura 10 · Fundamentos 20 · Mini-proyecto 25 · Cierre 5) |
| **Pre-requisitos** | Navegación web, correo y Google Drive. Sin programación. |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **Aplicar prompts estructurados** (Rol + Tarea + Contexto + Formato) y distinguir output libre vs estructurado.
2. **Construir un escenario en Make** conectando Google vía OAuth (Google Cloud Project: Client ID + Secret).
3. **Integrar Gemini** dentro del flujo generando una API key en Google AI Studio.
4. **Procesar la respuesta de la IA** con Data Structure y Parse JSON, convirtiendo texto en variables.

---

## Caso guía y evaluación

- **Caso guía:** el sistema de automatización de **facturas** (Drive → Make → IA → Sheet). Sin protagonista nombrado.
- **Evaluación:** práctica en clase **0/100** por sesión. Sin entregables post-clase.
- **Test diagnóstico:** al cierre de la Sesión 4 (control interno, no califica).

---

## Evolución por Sesión

| Sesión | Enfoque | Resultado al finalizar |
|--------|---------|------------------------|
| 1 | Prompts efectivos | 3 prompts profesionales probados (clasificar, resumir, redactar) |
| 2 | Make 101 + Google Cloud | Escenario Drive → Sheet (registro de facturas, sin IA) |
| 3 | API key de Gemini | Gemini en el escenario extrayendo el proveedor de la factura |
| 4 | JSON + Parse JSON | Ventas desde Gmail → JSON → columnas del Sheet |

---

## Arquitectura de Sesiones

### Sesión 1 — Prompts efectivos
- **Concepto:** la anatomía del prompt (Rol + Tarea + Contexto + Formato) y output libre vs estructurado.
- **Mini-proyecto:** 3 prompts profesionales para tareas reales.
- **Herramienta nueva:** Gemini (chat).

### Sesión 2 — Make 101 + Google Cloud
- **Concepto:** qué es Make, anatomía del escenario (trigger → módulos → acción), OAuth, Google Cloud Project.
- **Mini-proyecto:** registro automático de facturas (Drive Watch → Sheets Add a Row).
- **Herramientas nuevas:** Make, Google Cloud.

### Sesión 3 — API key de Gemini
- **Concepto:** qué es una API y una API key; Connection vs key directa; Flash vs Pro.
- **Mini-proyecto:** Gemini lee la factura y extrae el proveedor a una columna.
- **Herramienta nueva:** Gemini API (Google AI Studio).

### Sesión 4 — JSON + Parse JSON (cierre de módulo)
- **Concepto:** qué es JSON, por qué pedir JSON a la IA, Data Structure, Parse JSON + variables.
- **Mini-proyecto:** extracción de ventas desde Gmail → JSON → columnas del Sheet.
- **Herramientas nuevas:** Parse JSON / Data Structure, Gmail en Make.
- **Test diagnóstico:** 5 preguntas (Sesiones 1-4).

---

## Conexión con el Módulo 2

| M1 establece | M2 escala |
|--------------|-----------|
| Datos estructurados en el Sheet (JSON/Parse) | Plantillas que los convierten en documentos |
| Gemini extrayendo datos | Flujo end-to-end robusto con filtros, routers y errores |
| El caso guía de facturas | El proyecto integrador propio del estudiante |
