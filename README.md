# AI 101 — IA estratégica para Profesionales

> En 4 semanas construirás un sistema automatizado que recolecta datos reales de tu trabajo y genera reportes ejecutivos con insights de IA — todo con herramientas 100% gratuitas.

Guía completa del curso AI 101: de profesional a operador de sistemas con IA.

---

## Formato del Curso

| Aspecto | Detalle |
|---------|---------|
| **Total de sesiones** | 8 sesiones sincrónicas |
| **Duración por sesión** | 2.5h en vivo |
| **Carga total** | 20 horas académicas (4 semanas × 2 sesiones) |
| **Estructura** | 2 módulos × 4 sesiones |
| **Modalidad** | 100% online en vivo (cohort-based) |
| **Práctica** | 80% de cada sesión es laboratorio |
| **Prerequisitos** | Navegación web, correo, Google Drive. **Sin programación**. Sin experiencia previa en IA. |

---

## El caso guía: Roberto

Todo el curso gira alrededor de un caso real. **Roberto** es gerente de una pequeña empresa con 3-4 vendedores:

**Dolor actual:**
- Cada vendedor reporta a su manera (WhatsApp, llamadas, correos dispersos)
- Pierde horas cada viernes consolidando datos manualmente
- Arma el reporte ejecutivo a mano
- No tiene visibilidad en tiempo real del desempeño del equipo

**Solución que construyes durante el curso:**
- Los vendedores envían correos informales → el sistema registra todo automáticamente
- Cada viernes 4pm llega el reporte ejecutivo listo al correo del gerente
- Los insights los genera Gemini con el contexto del negocio
- Roberto recupera 4-8 horas semanales

En el **Módulo 1** construyes el sistema piezas por pieza usando el caso Roberto. En el **Módulo 2** lo integras con IA, lo optimizas, y luego lo **adaptas a tu propio caso de trabajo** para presentarlo en Demo Day.

---

## Estructura del Curso

```
┌──────────────────────────────────────────────────────────────────┐
│                       AI 101 (4 semanas)                         │
├────────────────────────────────┬─────────────────────────────────┤
│   MÓDULO 1 (Semanas 1-2)       │    MÓDULO 2 (Semanas 3-4)       │
│   Piezas del sistema           │    Integración y proyecto       │
├────────────────────────────────┼─────────────────────────────────┤
│ 1. Prompts y Gems              │ 5. Gemini API + 2 flujos        │
│ 2. Google Sheets con IA        │ 6. Integración total            │
│ 3. Google Slides con IA        │ 7. Tu proyecto propio           │
│ 4. Make básico (sin IA)        │ 8. Demo Day + ROI + plan 30d    │
└────────────────────────────────┴─────────────────────────────────┘
```

---

## Resultados de Aprendizaje

Al completar el programa, el participante podrá:

1. **Diseñar prompts efectivos** aplicando la estructura Rol + Contexto + Tarea + Formato + Restricciones, y configurar Gems personalizados en Gemini.
2. **Estructurar datos para automatización** diseñando Google Sheets con 3 pestañas (operación, configuración, histórico) y rangos nombrados.
3. **Diseñar plantillas de reportes** en Google Slides con marcadores variables clasificados por tipo (crudo, calculado, generado por IA).
4. **Construir flujos automáticos en Make** usando Instant Trigger de Gmail, sin escribir código.
5. **Integrar Gemini API** en Make para extraer datos estructurados desde texto libre y generar insights contextuales.
6. **Optimizar prompts y aplicar mejores prácticas** de sistemas automatizados (storytelling, nombres con fecha, respaldos, logs, alertas).
7. **Aplicar el sistema a un caso real** de su trabajo, adaptando datos, marca y prompts.
8. **Presentar el sistema calculando ROI** en horas ahorradas y proyectar un plan de 30 días con próximas automatizaciones.

---

## Módulo 1: Piezas del Sistema (Sesiones 1-4)

El estudiante aprende una pieza por sesión y acumula un inventario de artefactos que integrará en el Módulo 2.

| # | Clase | Contenido | Entregable |
|---|-------|-----------|------------|
| 1 | [Prompts y Gems](curriculum/class-01/) | Cómo funciona la IA, tokens y alucinaciones, anatomía del prompt profesional, creación de Gems con archivos | Brief del proyecto de instrucción (1 párrafo) + Gem personalizado funcionando + 3 prompts probados |
| 2 | [Google Sheets con IA](curriculum/class-02/) | Por qué la IA necesita estructura, arquitectura de 3 pestañas (operación + config + histórico), rangos nombrados | Sheet con 3 pestañas + 15 filas de ejemplo + tabla de parámetros |
| 3 | [Google Slides con IA](curriculum/class-03/) | Anatomía del reporte ejecutivo (6 secciones), 3 tipos de marcadores (crudo/calculado/IA), paleta y jerarquía | Plantilla de Slides + tabla de ~18-20 marcadores clasificados |
| 4 | [Make básico (sin IA)](curriculum/class-04/) | Conceptos de Make (escenario, módulo, operación, trigger), Instant vs Scheduled, Replace Text en Slides | 2 escenarios de Make funcionando: Gmail→Sheet (instant) + Sheet→Slides→PDF→Gmail (manual) |

### Salida del Módulo 1

- Brief del proyecto de instrucción validado
- Gem personalizado como asistente del curso
- Google Sheet con 3 pestañas y rangos nombrados
- Plantilla de Slides con marcadores documentados
- 2 flujos de Make funcionando sin IA
- Tabla de parámetros actualizada (documento vivo del curso)

---

## Módulo 2: Integración y Proyecto (Sesiones 5-8)

El estudiante integra las piezas con IA, optimiza el sistema, lo adapta a su caso real y lo presenta.

| # | Clase | Contenido | Entregable |
|---|-------|-----------|------------|
| 5 | [Gemini API + 2 flujos](curriculum/class-05/) | API, HTTP, JSON, API key gratis (1,500 req/día), extracción de datos desde correos informales, generación de insights | Sistema modelo completo: flujo instantáneo activo + flujo semanal scheduled con IA |
| 6 | [Integración total](curriculum/class-06/) | Prompt engineering avanzado (chain of thought, few-shot, persona), storytelling de datos, mejores prácticas (nombres con fecha, respaldos, alertas, logs) | Prompts optimizados (antes/después) + sistema con 4 mejores prácticas + plan de personalización (5 puntos) |
| 7 | [Tu proyecto propio](curriculum/class-07/) | Los 5 puntos críticos de personalización, acompañamiento 1 a 1, debug de flujos en Make | Sistema propio funcionando con datos reales (Sheet + Slides con marca + 2 flujos adaptados) |
| 8 | [Demo Day + ROI](curriculum/class-08/) | Estructura PSDR (Problema-Solución-Demo-Resultado), cálculo de ROI, plan 30 días con 3 próximos agentes | Demo grabado + ROI calculado (mensual y anual) + plan 30 días + rúbricas de pares |

### Salida del Módulo 2

- Sistema automatizado funcionando para un caso real del estudiante
- Prompts optimizados con storytelling (antes/después documentado)
- ROI calculado en soles con proyección mensual y anual
- Plan 30 días con 3 automatizaciones priorizadas (80/20)
- Demo en vivo presentado ante pares con feedback de rúbrica

---

## El Proyecto de Instrucción (hilo conductor)

Cada estudiante define en la Sesión 1 un **proyecto de instrucción**: un reporte real de su trabajo que quiere automatizar. Ese proyecto acompaña las 8 sesiones — cada sesión produce un artefacto que se integra al sistema final.

### Evolución clase a clase

| Clase | Pieza del Sistema |
|-------|-------------------|
| 1 | Brief del proyecto + Gem asistente |
| 2 | Google Sheet con 3 pestañas estructurado |
| 3 | Plantilla de Slides con ~18-20 marcadores documentados |
| 4 | 2 flujos de Make funcionando sin IA |
| 5 | Sistema modelo con Gemini API integrada (flujo instantáneo + semanal) |
| 6 | Prompts optimizados + mejores prácticas + plan de personalización |
| 7 | Sistema propio adaptado al caso real del estudiante |
| 8 | Demo en vivo + cálculo de ROI + plan 30 días |

### Entregables Finales

- Sistema de automatización funcionando con datos reales de tu trabajo
- Reporte ejecutivo en PDF llegando automáticamente a tu correo
- Cálculo de ROI documentado (horas ahorradas × tarifa)
- Plan de 30 días con 3 próximos agentes a construir
- Presentación grabada para compartir en LinkedIn o con tu equipo

---

## Evaluación

| Componente | Criterio | Peso |
|------------|----------|------|
| Entregables de sesión (8) | Completado y presentado en plazo | 40% |
| Participación en labs en vivo | Asistencia activa ≥ 75% de sesiones | 20% |
| Lab calificado M1 (Clase 4) | 2 flujos de Make funcionando end-to-end | 15% |
| Sistema propio (Clase 7) | Sistema adaptado funcionando con datos reales | 10% |
| Demo Day (Clase 8) | Demo en vivo de 5 minutos + ROI + plan 30 días | 15% |

**Aprobación:** Puntaje mínimo 70/100. Asistencia mínima: 6 de 8 sesiones.

---

## Stack de Herramientas — 100% gratuito

Todas las herramientas funcionan con plan gratuito. **No se requiere tarjeta de crédito**.

| Herramienta | Plan | Uso en el programa | Clase |
|-------------|------|--------------------|-------|
| **Gemini** | Free | Chat base, diseño de prompts, asistente del curso | 1-8 |
| **Gemini Gems** | Free | Asistentes personalizados con contexto fijo | 1-8 |
| **Gemini API** | Free (1,500 req/día) | Extracción de datos y generación de insights en Make | 5-8 |
| **Make** | Free (1,000 ops/mes) | Plataforma de automatización visual sin código | 4-8 |
| **Google Sheets** | Free | Fuente de datos estructurados (3 pestañas) | 2-8 |
| **Google Slides** | Free | Plantilla del reporte ejecutivo con marcadores | 3-8 |
| **Gmail** | Free | Entrada de datos (Instant Trigger) y entrega del PDF | 4-8 |

---

## Estructura de Archivos por Clase

```
curriculum/class-XX/
├── README.md           # Resumen + preparación del estudiante
├── lab/
│   └── README.md       # Guía de taller paso a paso
├── slides/
│   └── README.md       # Presentación reveal.js
├── facilitator/
│   └── README.md       # Guía pedagógica para instructor
└── infographic/
    ├── index.html      # Infografía post-clase (WhatsApp/LinkedIn)
    └── image-prompts.md
```

Las clases 4 y 8 incluyen además `lab/rubric.md` (rúbrica de evaluación) y `test/` (test diagnóstico del módulo).

---

## Ruta AI Solutions

```
AI 101: IA estratégica para Profesionales (4 semanas / 20h)  ← Estás aquí
   → Sistema automatizado de reportes
   → Gemini + Make + Google Workspace

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
│   ├── module-1/              # Plan del Módulo 1
│   ├── class-01/              # Prompts y Gems
│   ├── class-02/              # Google Sheets con IA
│   ├── class-03/              # Google Slides con IA
│   ├── class-04/              # Make básico (sin IA)
│   ├── module-2/              # Plan del Módulo 2
│   ├── class-05/              # Gemini API + 2 flujos
│   ├── class-06/              # Integración total
│   ├── class-07/              # Tu proyecto propio
│   └── class-08/              # Demo Day + ROI
├── resources/
│   ├── prompts/               # Biblioteca de prompts de referencia
│   └── templates/             # Plantillas (Gem, Sheet, Slides, Blueprints Make)
└── dev/
    └── nuevo_silabus_walter/  # Material fuente del instructor (sílabo + PPTs)
```

---

## Para Facilitadores

- Ver [AGENTS.md](AGENTS.md) para convenciones del repositorio y pipeline de generación
- Cada clase tiene su carpeta con: `README`, `lab/`, `slides/`, `facilitator/`, `infographic/`
- 80% práctica en cada clase, sin grabaciones como recurso principal
- El proyecto de instrucción es el hilo conductor — todo entregable se reusa en la siguiente sesión

---

*Enter Tech School — Formando profesionales que automatizan su trabajo con IA*
