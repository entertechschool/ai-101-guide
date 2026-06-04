# AI 101 — IA + Automatización No-Code para Profesionales

> En 8 sesiones construirás soluciones automatizadas que integran inteligencia artificial con herramientas no-code (Make + Gemini + Google Workspace) para resolver problemas reales de tu trabajo — todo sin escribir código.

Guía completa del curso AI 101: de profesional a constructor de automatizaciones con IA.

---

## Formato del Curso

| Aspecto | Detalle |
|---------|---------|
| **Total de sesiones** | 8 sesiones sincrónicas |
| **Duración por sesión** | 60 min en vivo |
| **Carga total** | 8 horas |
| **Estructura** | 8 sesiones (clases en vivo) |
| **Modalidad** | Online sincrónica (clases en vivo) |
| **Práctica** | Cada sesión incluye un mini-proyecto en vivo que produce un entregable concreto |
| **Audiencia** | Profesionales sin formación técnica que buscan automatizar tareas con IA. **Sin programación.** |

### Estructura de cada sesión (60 min)

| Momento | Duración | Propósito |
|---------|----------|-----------|
| **Apertura** | 10 min | Preguntas al grupo para conectar con la realidad del estudiante y diagnosticar |
| **Teoría / Fundamentos** | 20 min | Conceptos clave de la sesión, cada uno con visual conceptual + ejemplo real |
| **Mini-proyecto** | 25 min | Práctica en vivo que produce un entregable que se suma al sistema |
| **Cierre** | 5 min | Síntesis de lo aprendido + conexión con la próxima sesión |

---

## Capacidad general del curso

Construir soluciones automatizadas que integran inteligencia artificial usando herramientas no-code (Make + Gemini + Google Workspace) para resolver problemas reales del entorno profesional.

---

## El caso guía: el sistema de facturas

Las sesiones 2 a 6 construyen, pieza por pieza, un mismo sistema real: la **automatización de facturas**.

**Dolor actual:**
- Las facturas llegan dispersas (correo, Drive, papel) y se registran a mano
- Alguien transcribe proveedor, montos y fechas a una hoja de cálculo
- El reporte mensual se arma manualmente, copiando y pegando
- Si algo se cae, nadie se entera hasta tarde

**Solución que construyes durante el curso:**
- Subes una factura a Drive → Make la detecta automáticamente
- Gemini lee el documento y extrae los datos (proveedor, monto, fecha)
- Los datos caen estructurados en un Google Sheet
- Cada mes se genera un reporte con plantilla y se envía por correo
- El flujo tiene filtros, manejo de errores y alertas si algo falla

En las **sesiones 1 a 6** aprendes cada pieza sobre el caso facturas (y casos paralelos como clasificar correos o extraer ventas desde Gmail). En las **sesiones 7 y 8** construyes y presentas tu **proyecto integrador propio**, aplicando todo a un caso real de tu trabajo.

---

## Estructura del Curso

```
┌──────────────────────────────────────────────────────────────────┐
│              AI 101 — 8 sesiones × 60 min = 8 horas              │
├────────────────────────────────┬─────────────────────────────────┤
│   PIEZAS DEL SISTEMA (1-6)     │    TU PROYECTO (7-8)            │
│   Caso guía: facturas          │    Caso propio del estudiante   │
├────────────────────────────────┼─────────────────────────────────┤
│ 1. Prompts efectivos           │ 7. Proyecto integrador          │
│ 2. Make 101 + Google Cloud     │ 8. Exposición / Demo Day        │
│ 3. API key de Gemini           │                                 │
│ 4. JSON + Parse JSON           │                                 │
│ 5. Plantillas con placeholders │                                 │
│ 6. Flujo end-to-end robusto    │                                 │
└────────────────────────────────┴─────────────────────────────────┘
```

---

## Resultados de Aprendizaje

Al completar el programa, el participante podrá:

1. **Aplicar prompts estructurados** (rol + tarea + contexto + formato) usando asistentes de IA generativa para obtener respuestas precisas en tareas profesionales.
2. **Construir un escenario en Make** conectando una cuenta Google vía OAuth, entendiendo OAuth y Google Cloud Project (Client ID + Secret).
3. **Integrar el modelo Gemini** dentro de un flujo de Make generando una API key en Google AI Studio.
4. **Procesar la respuesta estructurada de la IA** con el módulo Parse JSON y un Data Structure para convertir texto en variables que el flujo entiende.
5. **Generar documentos y presentaciones automáticas** usando plantillas con placeholders `{{variable}}` en Docs/Slides.
6. **Diseñar un flujo end-to-end robusto** (Watch vs Schedule, filtros, routers, manejo de errores, logs) que automatiza un proceso real de principio a fin.
7. **Construir un proyecto integrador propio** aplicando todo lo aprendido para resolver un caso real de su trabajo o emprendimiento.
8. **Sustentar el proyecto integrador** en Demo Day, evidenciando decisiones técnicas, resultados y aprendizajes.

---

## Las 8 Sesiones

| # | Sesión | Objetivo de aprendizaje | Mini-proyecto (entregable) |
|---|--------|-------------------------|----------------------------|
| 1 | [Prompts efectivos](curriculum/class-01/) | Aplicar prompts estructurados para obtener respuestas precisas en tareas profesionales | 3 prompts profesionales: clasificar correos, resumir reunión, redactar respuesta de venta |
| 2 | [Make 101 + Google Cloud](curriculum/class-02/) | Construir un primer escenario en Make conectando Google vía OAuth | Registro automático de facturas: Drive → Make → fila en Sheet (sin IA aún) |
| 3 | [API key de Gemini](curriculum/class-03/) | Integrar Gemini dentro del flujo generando una API key en Google AI Studio | La factura pasa por Gemini → extrae el proveedor → columna nueva en el Sheet |
| 4 | [JSON + Parse JSON](curriculum/class-04/) | Procesar la respuesta de la IA con Parse JSON y un Data Structure | Extracción de ventas desde Gmail → JSON → cada campo en su columna del Sheet |
| 5 | [Plantillas con placeholders](curriculum/class-05/) | Generar documentos/presentaciones con plantillas y placeholders `{{variable}}` | Reporte mensual de facturas: Sheet → Slide con plantilla → Drive/email |
| 6 | [Flujo end-to-end robusto](curriculum/class-06/) | Diseñar un flujo completo Drive → IA → Sheets/Docs/Gmail | Flujo completo de facturas con filtros, router, manejo de errores y alertas |
| 7 | [Proyecto integrador](curriculum/class-07/) | Construir un proyecto propio que resuelve un caso real | Tu flujo v1 funcionando con datos reales de tu trabajo |
| 8 | [Exposición / Demo Day](curriculum/class-08/) | Sustentar el proyecto integrador ante la clase | Demo en vivo de 5 min: caso → demo → resultados → Q&A |

---

## El Proyecto Integrador (sesiones 7-8)

Durante las sesiones 1 a 6 el estudiante aprende cada pieza sobre el caso guía de facturas. En la **sesión 7** elige un **caso real propio** (contabilidad, atención al cliente, marketing, ventas, RR.HH., etc.), lo diagrama y construye una primera versión de su flujo con datos reales. En la **sesión 8** lo presenta en Demo Day.

### Entregables finales

- Un flujo automatizado propio funcionando con datos reales de tu trabajo
- Resultado tangible del sistema (documento, reporte o registro generado automáticamente)
- Demo en vivo presentado ante pares con feedback
- Roadmap personal: la próxima automatización a construir

---

## Evaluación

| Componente | Criterio |
|------------|----------|
| **Práctica en clase** | Cada sesión incluye un reto/mini-proyecto en vivo. El docente califica **0 (no hizo) / 100 (sí hizo)**. **No hay entregables post-clase.** |
| **Proyecto integrador (S7)** | Cada estudiante construye su proyecto propio con datos reales |
| **Demo Day (S8)** | Exposición del proyecto integrador ante la clase |
| **Asistencia y participación** | Asistencia a las 8 sesiones + participación en la Apertura y el Cierre de cada una |

> El sistema se centra en la práctica en vivo: lo que importa es que el estudiante **construya durante la clase**, no que entregue tareas después.

---

## Stack de Herramientas — 100% gratuito

Todas las herramientas funcionan con plan gratuito. **No se requiere tarjeta de crédito.**

| Herramienta | Plan | Uso en el programa | Sesión |
|-------------|------|--------------------|--------|
| **Gemini** | Free | Chat base, diseño y prueba de prompts | 1 |
| **Make** | Free (1,000 ops/mes) | Plataforma de automatización visual sin código | 2-8 |
| **Google Cloud** | Free | Proyecto con Client ID + Secret para conectar Google vía OAuth | 2 |
| **Google Drive** | Free | Entrada de archivos (trigger) y almacenamiento | 2-8 |
| **Google Sheets** | Free | Fuente de datos estructurados | 2-8 |
| **Gemini API** | Free (Google AI Studio) | Extracción de datos y generación de insights dentro de Make | 3-8 |
| **Gmail** | Free | Entrada de datos (Watch) y entrega de reportes | 4-8 |
| **Google Docs / Slides** | Free | Plantillas con placeholders para reportes automáticos | 5-8 |

---

## Estructura de Archivos por Clase

```
curriculum/class-XX/
├── README.md           # Resumen + preparación del estudiante
├── lab/
│   └── README.md       # Mini-proyecto paso a paso
├── slides/
│   └── README.md       # Presentación reveal.js
├── facilitator/
│   └── README.md       # Guía pedagógica para instructor
└── infographic/
    ├── index.html      # Infografía post-clase (WhatsApp/LinkedIn)
    └── image-prompts.md
```

Las clases 4 y 8 incluyen además `test/` (test diagnóstico).

---

## Ruta AI Solutions

```
AI 101: IA + Automatización No-Code para Profesionales (8 sesiones / 8h)  ← Estás aquí
   → Sistema automatizado con IA
   → Make + Gemini + Google Workspace

         ↓

AI 201: Construye con IA (8 semanas / 80h)
   → Crear soluciones no-code más amplias
   → Producto/herramienta funcional

         ↓

AI 301: Escala con IA (10 semanas / 100h)
   → Integración técnica
   → Proyecto profesional/startup
```

---

## Estructura del Repositorio

```
ai-101-guide/
├── README.md                  # ← Fuente de verdad (este archivo)
├── AGENTS.md                  # Instrucciones para agentes AI
├── CLAUDE.md                  # Convenciones de Claude Code
├── curriculum/
│   ├── class-00/              # Orientación del curso
│   ├── class-01/              # Prompts efectivos
│   ├── class-02/              # Make 101 + Google Cloud
│   ├── class-03/              # API key de Gemini
│   ├── class-04/              # JSON + Parse JSON
│   ├── class-05/              # Plantillas con placeholders
│   ├── class-06/              # Flujo end-to-end robusto
│   ├── class-07/              # Proyecto integrador
│   └── class-08/              # Exposición / Demo Day
├── resources/
│   ├── prompts/               # Biblioteca de prompts de referencia
│   └── templates/             # Plantillas (Sheet, Slides, Blueprints Make)
└── fuente/                    # Material fuente del instructor (sílabo v3 + PPTs)
```

---

## Para Facilitadores

- Ver [AGENTS.md](AGENTS.md) para convenciones del repositorio y pipeline de generación
- Cada clase tiene su carpeta con: `README`, `lab/`, `slides/`, `facilitator/`, `infographic/`
- Cada sesión es de 60 min con estructura fija: Apertura (10') → Fundamentos (20') → Mini-proyecto (25') → Cierre (5')
- El caso guía de facturas hila las sesiones 1-6; el proyecto propio cierra en las sesiones 7-8

---

*Enter Tech School — Formando profesionales que automatizan su trabajo con IA*
