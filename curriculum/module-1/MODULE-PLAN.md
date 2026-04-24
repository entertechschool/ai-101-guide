# Plan del Módulo 1: Piezas del Sistema

> Este documento define la arquitectura del módulo. Aprobar antes de crear clases.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | 1 |
| **Título** | Piezas del Sistema |
| **Tema Central** | Construir pieza por pieza el sistema modelo alrededor del caso Roberto |
| **Clases** | 1 a 4 |
| **Duración por clase** | 2.5h sincrónicas |
| **Pre-requisitos** | Manejo básico de navegación web, correo electrónico y Google Drive |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **Diseñar prompts efectivos y Gems personalizados** — Aplicar la estructura Rol+Contexto+Tarea+Formato+Restricciones y configurar un Gem con archivos de referencia como asistente persistente.
2. **Estructurar datos para automatización** — Diseñar un Google Sheet con 3 pestañas (operación, configuración, histórico) y definir rangos nombrados.
3. **Diseñar plantillas de reportes con marcadores** — Crear una plantilla de Google Slides con 6 secciones y ~18-20 marcadores clasificados por tipo (crudo, calculado, IA).
4. **Construir flujos automáticos en Make sin IA** — Usar Instant Trigger de Gmail, conectar Sheets con Slides (Replace Text) y cerrar el flujo con exportación de PDF por correo.

---

## Portfolio del Módulo

### Descripción

Durante las primeras 4 sesiones, el estudiante construye las **piezas individuales** del sistema modelo (el de Roberto). Cada sesión produce un artefacto concreto que la siguiente sesión usa como base. Al cerrar el Módulo 1, el estudiante tiene un sistema que ya funciona end-to-end — pero todavía sin IA en el flujo.

El Módulo 1 establece el **hábito de trabajar con un artefacto vivo**: el proyecto de instrucción del estudiante (su reporte real que quiere automatizar) y la **tabla de parámetros** que acumula decisiones (columnas del Sheet, marcadores de Slides, rangos nombrados, nombres de pestañas). Esta tabla es el documento de referencia para el Módulo 2.

### Evolución por Clase

| Clase | Enfoque | Pieza del Sistema al Finalizar |
|-------|---------|---------------------------------|
| 1 | Prompts + Gem asistente | Brief del proyecto de instrucción + Gem con instrucciones y archivo de referencia + 3 prompts probados |
| 2 | Sheet estructurado | Google Sheet con 3 pestañas (operación + config + histórico) + 15 filas de ejemplo + tabla de parámetros iniciada |
| 3 | Plantilla de Slides | Plantilla de Slides con 6 slides + tabla con ~18-20 marcadores clasificados por tipo |
| 4 | 2 flujos de Make sin IA | Escenario 1 (Gmail→Sheet instant) + Escenario 2 (Sheet→Slides→PDF→Gmail manual) funcionando |

### Entregables del Módulo

Al finalizar M1, el estudiante tiene:
- Brief del proyecto de instrucción (1 párrafo) validado
- Gem personalizado funcionando con al menos 1 archivo de referencia
- Google Sheet con 3 pestañas, 15 filas de ejemplo y rangos nombrados
- Plantilla de Slides con 6 secciones y marcadores documentados
- Tabla de parámetros actualizada (columnas + marcadores + nombres + rangos)
- 2 escenarios de Make funcionando sin IA

---

## Arco Narrativo del Módulo

```
C01: "La IA funciona mejor con contexto fijo"  → Gem + brief del proyecto
C02: "La IA necesita estructura para automatizar" → Sheet con 3 pestañas
C03: "Un reporte vive de marcadores variables"   → Plantilla de Slides + marcadores
C04: "Make conecta las piezas sin código"        → 2 flujos end-to-end (sin IA aún)
```

El Módulo 1 es estrictamente **constructivo**: no hay optimización ni personalización todavía. El estudiante sigue el caso Roberto paso a paso y acumula artefactos que en M2 se integran con IA y se adaptan a su caso real.

---

## Arquitectura de Clases

### Clase 1: Prompts y Gems

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | La IA predice palabras probables — la estructura del prompt cambia 10x los resultados |
| **Objetivo del Lab** | Diseñar 3 prompts profesionales + definir brief + crear Gem asistente |
| **Herramientas** | Gemini (chat), Gemini Gems |
| **Entregable** | Brief del proyecto de instrucción (1 párrafo) + Gem funcionando con archivo + 3 prompts probados |

**Actividades del Lab:**
1. **Actividad 1 (35 min):** Mejorar un prompt genérico aplicando Rol+Contexto+Tarea+Formato+Restricciones. Probar 3 variaciones.
2. **Actividad 2 (35 min):** Escribir brief de 1 párrafo con plantilla (qué reporte, frecuencia, destinatario, datos, tiempo estimado).
3. **Actividad 3 (40 min):** Crear Gem con nombre, instrucciones, al menos 1 archivo de referencia y probar con tareas reales.

**Checkpoints del Lab:**
1. Tres prompts del mismo tema con resultados visibles (genérico → parcial → completo)
2. Brief en Google Doc con la plantilla de 4 elementos
3. Gem respondiendo con el contexto del brief

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| LLM | Large Language Model — modelo de IA que predice la siguiente palabra probable |
| Token | Unidad que procesa la IA (~3/4 de una palabra en español) |
| Alucinación | Cuando la IA inventa información con apariencia creíble |
| Prompt profesional | Estructura Rol + Contexto + Tarea + Formato + Restricciones |
| Gem | Asistente personalizado de Gemini con instrucciones y archivos fijos |
| Brief | Resumen de 1 párrafo del proyecto de instrucción del estudiante |

**Dependencias:**
- **Requiere:** Nada técnico (cuenta de Gemini creada)
- **Habilita:** Clase 2 usa el Gem para diseñar el Sheet; el brief guía todo el proyecto de instrucción del curso

---

### Clase 2: Google Sheets con IA

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | La IA y la automatización necesitan datos estructurados — arquitectura de 3 pestañas (operación + config + histórico) |
| **Objetivo del Lab** | Diseñar y construir un Sheet con 3 pestañas usando el Gem como copiloto |
| **Herramientas** | Google Sheets (nueva), Gemini (ya conocida) |
| **Entregable** | Sheet con 3 pestañas + 15 filas de ejemplo + tabla de parámetros actualizada |

**Actividades del Lab:**
1. **Actividad 1 (40 min):** Diseñar pestaña `VentasSemanaActual` con Gemini, columnas mínimas (Fecha, Vendedor, Cliente, Producto, Monto, Tipo, Descripción), 15 filas de ejemplo.
2. **Actividad 2 (25 min):** Construir pestaña `Config` con parámetros del negocio (meta, ticket objetivo, vendedores) usando valores reales del estudiante.
3. **Actividad 3 (35 min):** Construir pestaña `Historico` + definir rangos nombrados (`RangoVentas`, `RangoConfig`, `RangoHistorico`).

**Checkpoints del Lab:**
1. Pestaña `VentasSemanaActual` con 7 columnas y 15 filas
2. Pestaña `Config` con al menos 4 parámetros del negocio
3. Pestaña `Historico` + 3 rangos nombrados visibles en Datos → Rangos con nombre

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Datos estructurados | Información organizada en tabla (columnas consistentes) vs texto libre |
| Rango nombrado | Apodo para un rango de celdas (ej: "RangoVentas" = `VentasSemanaActual!A:G`) |
| Pestaña operativa | Donde llegan los datos crudos del día a día |
| Pestaña de configuración | Parámetros del negocio que no cambian (meta, equipo) |
| Pestaña histórica | Memoria que se acumula semana a semana para comparar |

**Dependencias:**
- **Requiere:** Clase 1 (Gem funcionando, brief definido)
- **Habilita:** Clase 3 usa el Sheet como origen de datos de los marcadores; Clase 4 lo conecta con Make

---

### Clase 3: Google Slides con IA

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Un reporte ejecutivo = partes fijas + marcadores variables clasificados por tipo |
| **Objetivo del Lab** | Diseñar plantilla de Slides con 6 secciones + nombrar todos los marcadores |
| **Herramientas** | Google Slides (nueva), Gemini (ya conocida) |
| **Entregable** | Plantilla de Slides con 6 slides + tabla de ~18-20 marcadores clasificados |

**Actividades del Lab:**
1. **Actividad 1 (30 min):** Pedir al Gem las 6 secciones del reporte según el brief. Crear plantilla con 6 slides (Portada, Resumen, Hallazgos, Visualización, Riesgos/Oportunidades, Próximos pasos).
2. **Actividad 2 (45 min):** Nombrar todos los marcadores en snake_case y clasificar en la tabla de parámetros (tipo: crudo/calculado/IA, origen, ejemplo). Meta: 18-20.
3. **Actividad 3 (25 min):** Insertar marcadores `{{nombre}}` en cada slide + prueba manual reemplazando 3-4 con datos reales + gráfico vinculado al Sheet.

**Checkpoints del Lab:**
1. Plantilla con 6 slides con títulos y diseño visual inicial
2. Tabla de parámetros con ~18-20 filas clasificadas por tipo + origen
3. Plantilla con marcadores `{{...}}` visibles + 3-4 reemplazados manualmente

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Marcador | Texto tipo `{{ventas_total}}` que Make reemplaza por un valor |
| Marcador crudo | Viene directo del Sheet (tipo 1) |
| Marcador calculado | Make lo calcula con fórmula (tipo 2) |
| Marcador generado por IA | Gemini lo crea desde los datos (tipo 3) |
| snake_case | Convención: todo en minúsculas, separado por guion bajo |
| Replace Text | Operación de Slides en Make que busca `{{x}}` y lo reemplaza |

**Dependencias:**
- **Requiere:** Clase 2 (Sheet con estructura clara)
- **Habilita:** Clase 4 conecta Sheet → Slides con Replace Text por cada marcador

---

### Clase 4 (Cierre de Módulo): Make básico (sin IA)

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Make = módulos + triggers + operaciones. Instant vs Scheduled. Todavía sin IA en el flujo. |
| **Objetivo del Lab** | Construir 2 escenarios: Gmail→Sheet (instant) y Sheet→Slides→PDF→Gmail (manual) |
| **Herramientas** | Make (nueva), Gmail en Make (nueva). Sheets y Slides ya conocidas. |
| **Entregable** | 2 escenarios de Make funcionando + al menos 5 marcadores tipo 1 y 2 reemplazados |
| **Test Diagnóstico** | 8 preguntas (15 min) — no afecta calificación |

**Actividades del Lab (formato calificado — 3 actividades + desafío post-clase):**
1. **Actividad 1 (40 min):** Escenario 1 — Gmail Watch Emails en modo Instant con filtro de asunto → Google Sheets Add a row. Probar con 3 correos.
2. **Actividad 2 (35 min):** Escenario 2 — Sheets Search Rows → Slides Create from Template → Replace Text (3-5 marcadores tipo 1 y 2 usando módulos Date y Math).
3. **Actividad 3 (25 min):** Cerrar el flujo con Slides Export as PDF → Gmail Send an Email con adjunto. Run once completo.
4. **Desafío post-clase (30-45 min):** Agregar manejo básico de errores (error handler) + nombre de PDF con fecha dinámica.

**Checkpoints del Lab:**
1. Escenario 1 activo: enviar correo y ver el Sheet actualizarse en <10 segundos
2. Escenario 2 corriendo: plantilla duplicada con valores reales en marcadores
3. PDF con marcadores reemplazados llega al correo del estudiante
4. (Desafío) Error handler + nombre con fecha: `Reporte_YYYY-MM-DD.pdf`

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Escenario | El flujo completo que construyes en Make |
| Módulo | Cada paso del flujo (leer Gmail, escribir en Sheet, etc.) |
| Operación | Cada vez que un módulo ejecuta (cuenta para el límite de 1,000/mes del plan free) |
| Conexión | Autenticación entre Make y tus cuentas (Gmail, Sheets, Slides) |
| Trigger | Módulo que inicia el flujo (Instant o Scheduled) |
| Instant Trigger | Se activa en 2-5 segundos cuando algo pasa (webhook o similar) |
| Scheduled Trigger | Corre cada X tiempo (cada 15 min, diario, semanal) |
| Replace Text | Busca `{{marcador}}` en Slides y lo sustituye por un valor |

**Dependencias:**
- **Requiere:** Clases 1-3 (Gem, Sheet con 3 pestañas, Slides con marcadores)
- **Habilita:** M2 (C05) integra la Gemini API en el mismo flujo; los marcadores tipo 3 (IA) se llenarán con prompts en HTTP módulos

---

## Conexión con Módulo 2

### Lo que M1 establece y M2 escala

| M1 Establece | M2 Escala |
|--------------|-----------|
| Gem asistente del curso | Prompts de producción con chain-of-thought y few-shot |
| Sheet con 3 pestañas vacías | Sheet acumulando datos reales + Historico lleno |
| Marcadores tipo 1 y 2 (crudo/calculado) | Marcadores tipo 3 generados por Gemini API |
| 2 flujos manuales sin IA | 2 flujos activos con IA (instantáneo + scheduled semanal) |
| Caso Roberto como referencia | Caso real del estudiante (C07) |
| Plantilla de Slides estándar | Slides con marca propia del estudiante |

### Semillas plantadas en M1 para M2

- C01 (Gem + brief) → C05 usa el brief para contexto del SystemPrompt de Gemini API
- C02 (Sheet + rangos nombrados) → C05 los referencia desde Make sin depender de coordenadas
- C03 (marcadores tipo 3 nombrados pero vacíos) → C05 los rellena con prompts JSON
- C04 (2 flujos sin IA) → C05 inserta módulos HTTP con Gemini API en esos mismos escenarios

---

## Checklist de Verificación

Antes de aprobar este plan, verificar:

- [x] Las 4 competencias son medibles con verbos de acción
- [x] Cada clase tiene UN concepto principal claro
- [x] Los checkpoints son verificables (visual: lo que debe verse en pantalla)
- [x] Las dependencias entre clases son explícitas
- [x] La clase 4 integra conceptos de las 3 anteriores (lab calificado + test)
- [x] Hay conexión clara con M2 (semillas → frutos)
- [x] El glosario cubre todos los términos nuevos
- [x] Herramientas nuevas respetan el límite de 2 por clase
- [x] README.md está alineado con este plan
