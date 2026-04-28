# Plan del Módulo 2: Integración y Proyecto

> Este documento define la arquitectura del módulo. Aprobar antes de crear clases.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | 2 |
| **Título** | Integración y Proyecto |
| **Tema Central** | Integrar IA al sistema modelo, optimizar, adaptar al caso real y presentar |
| **Clases** | 5 a 8 |
| **Duración por clase** | 2.5h sincrónicas |
| **Pre-requisitos** | Módulo 1 completo (Gem + Sheet + plantilla + 2 flujos Make sin IA) |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **Integrar Gemini API en Make** — Configurar una API key gratis, crear módulos HTTP que envían datos a Gemini y reciben JSON estructurado, y conectarlos a los escenarios del M1.
2. **Optimizar prompts para producción** — Aplicar chain-of-thought, few-shot y persona explícita; transformar insights "planos" en "accionables" con storytelling de datos.
3. **Aplicar el sistema a un caso real** — Adaptar el sistema modelo al caso real de trabajo del estudiante (datos propios, marca, métricas, prompts).
4. **Presentar con ROI y plan** — Estructurar una presentación PSDR de 5 min con demo en vivo, calcular ROI (horas × tarifa) y definir plan 30 días con 3 próximos agentes.

---

## Portfolio del Módulo

### Descripción

Durante las clases 5-8, el estudiante escala de "sistema modelo sin IA" (M1) a "sistema propio con IA que resuelve un problema real" (M2). El módulo tiene tres fases: integrar IA al sistema modelo (C05), optimizar y definir personalización (C06), transferir al caso real (C07), presentar y proyectar (C08).

La diferencia con M1: en M1 construiste piezas genéricas del caso Roberto. En M2 las integras con IA, las optimizas, y las haces tuyas. Al terminar, el sistema ya no es un ejercicio académico — es una automatización funcionando con TUS datos reales.

### Evolución por Clase

| Clase | Enfoque | Pieza del Sistema al Finalizar |
|-------|---------|--------------------------------|
| 5 | Gemini API en Make | Sistema modelo completo con 2 flujos activos: instantáneo (correo→Gemini→Sheet) + semanal (Sheet→Gemini→Slides→PDF) |
| 6 | Optimización + mejores prácticas | Prompts optimizados (antes/después) + 4 mejores prácticas aplicadas + plan de 5 puntos de personalización |
| 7 | Proyecto individual | Sistema personalizado con datos reales del estudiante (Sheet + Slides con marca + 2 flujos adaptados) |
| 8 | Demo Day + ROI + plan 30 días | Demo grabado + ROI documentado + plan 30 días con 3 próximos agentes |

### Entregables del Módulo

Al finalizar M2, el estudiante tiene:
- Sistema modelo con IA (flujos instantáneo y semanal activos para caso Roberto)
- Sistema propio para su caso real de trabajo
- Prompts optimizados con storytelling (antes/después documentado)
- ROI calculado (mensual y anual en soles reales)
- Plan 30 días con 3 automatizaciones priorizadas (80/20)
- Presentación grabada con demo en vivo de 5 minutos

---

## Arco Narrativo del Módulo

```
C05: "La IA entra al sistema"     → Gemini API llena marcadores tipo 3
C06: "El sistema mejora"          → Prompts optimizados + mejores prácticas
C07: "Ahora lo hago mío"          → Transferencia al caso real del estudiante
C08: "Lo presento y planifico"    → Demo + ROI + plan 30 días
```

La clase 5 es la **bisagra** del curso: es la primera vez que los marcadores tipo IA (`{{hallazgo_1}}`, `{{resumen_ejecutivo}}`) dejan de estar vacíos. Después, la clase 6 pule; la 7 personaliza; la 8 presenta.

---

## Arquitectura de Clases

### Clase 5: Gemini API + 2 flujos completos

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | API + HTTP + JSON — la IA entra al flujo y llena marcadores tipo 3 |
| **Objetivo del Lab** | Configurar API key, extraer datos desde correos informales, generar insights, dejar los 2 flujos activos |
| **Herramientas** | Gemini API (nueva, free 1,500 req/día), módulo HTTP en Make (nueva funcionalidad) |
| **Entregable** | Sistema modelo completo: flujo instantáneo activo + flujo semanal scheduled con IA integrada |

**Actividades del Lab:**
1. **Actividad 1 (45 min):** Obtener API key de Gemini → configurar módulo HTTP en Make con la key → modificar escenario 1 (Gmail → Gemini → Sheets) para que Gemini extraiga datos estructurados desde correos informales.
2. **Actividad 2 (40 min):** En el escenario 2, agregar HTTP a Gemini con datos del Sheet → generar JSON con resumen, hallazgos, riesgos, oportunidades → mapear cada campo a su marcador tipo IA en Slides.
3. **Actividad 3 (30 min):** Cambiar trigger del escenario 2 a Scheduled (viernes 4pm) → agregar Sheets Add a row al Historico al cierre → activar ambos escenarios → run once de prueba completa.

**Checkpoints del Lab:**
1. API key de Gemini configurada, HTTP module respondiendo con JSON válido
2. Escenario 1 procesa correos informales y agrega filas bien estructuradas al Sheet
3. Escenario 2 con scheduled trigger activo, PDF con insights generados por Gemini llega al correo
4. Historico se alimenta solo al final de cada corrida

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| API | Interfaz entre programas — analogía: mozo que pide a la cocina |
| API Key | Contraseña única que te identifica ante Gemini API |
| HTTP POST | Método de envío de datos a la API |
| JSON | Formato de datos estructurados `{clave: valor}` |
| Módulo HTTP en Make | Módulo genérico para llamar cualquier API |
| Rate limit | Límite de requests por día (Gemini free: 1,500/día) |

**Dependencias:**
- **Requiere:** Clases 1-4 (Gem, Sheet, plantilla, 2 flujos Make sin IA)
- **Habilita:** C06 (optimizar los prompts que se definen aquí)

---

### Clase 6: Integración total y mejores prácticas

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Un prompt optimizado cambia 10x la calidad del output. Mejores prácticas hacen el sistema sostenible. |
| **Objetivo del Lab** | Optimizar prompts con storytelling + aplicar 4 mejores prácticas + definir puntos de personalización |
| **Herramientas** | 0 nuevas (todo el stack del M1 + Gemini API de C05) |
| **Entregable** | Prompts optimizados (antes/después) + sistema con 4 mejores prácticas + plan de personalización |

**Actividades del Lab:**
1. **Actividad 1 (45 min):** Comparar 3 outputs (plano/mediocre/potente) → reescribir prompts con persona + few-shot + contexto → ejecutar y comparar antes/después.
2. **Actividad 2 (40 min):** Aplicar 4 mejores prácticas: (1) nombres de archivo con fecha dinámica, (2) carpeta Backups en Drive, (3) alertas por correo si el flujo falla, (4) pestaña Logs en Sheet.
3. **Actividad 3 (30 min):** Revisar brief original + definir 5 puntos críticos a personalizar en Clase 7 + actualizar tabla de parámetros para su caso propio.

**Checkpoints del Lab:**
1. Al menos 3 prompts reescritos con chain-of-thought o few-shot, con comparación antes/después documentada
2. Sistema con las 4 mejores prácticas aplicadas (file con fecha, Backups, alerta, Logs)
3. Plan de personalización con 5 puntos críticos y tabla de parámetros actualizada para caso propio

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Chain of thought | "Piensa paso a paso antes de responder" — técnica que mejora razonamiento |
| Few-shot | Dar ejemplos de output deseado dentro del prompt |
| Persona | Definir rol específico de la IA ("eres analista con 10 años de experiencia") |
| Storytelling de datos | Contextualizar números: comparar meta/anterior, explicar causa, sugerir acción |
| Error handler | Módulo que se activa si algún paso del flujo falla |
| Log | Registro persistente de ejecuciones (fecha, estado, duración) |

**Dependencias:**
- **Requiere:** C05 (sistema modelo con IA funcionando)
- **Habilita:** C07 (estudiante tiene prompts optimizados y plan de personalización listos)

---

### Clase 7: Tu proyecto propio

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Transferencia — aplicar el patrón a tu caso real; la arquitectura se queda, el cerebro cambia |
| **Objetivo del Lab** | Construir sistema personalizado con datos propios, marca propia, prompts propios |
| **Herramientas** | 0 nuevas (todo el stack de M1-M2) |
| **Entregable** | Sistema propio funcionando con datos reales (Sheet + Slides marca + 2 flujos adaptados) |

**Actividades del Lab (con acompañamiento 1 a 1):**
1. **Actividad 1 (50 min):** Duplicar Sheet modelo → renombrar columnas según su caso → adaptar Config con parámetros reales → llenar Historico con 2-3 semanas reales.
2. **Actividad 2 (50 min):** Duplicar plantilla Slides → aplicar marca (logo, colores, tipografía) → renombrar marcadores → duplicar los 2 escenarios de Make → reemplazar prompts con los propios.
3. **Actividad 3 (20 min):** Enviar 3 correos de prueba reales → verificar Sheet se actualiza → run once del flujo semanal → revisar PDF → activar scheduled con frecuencia real.

**Checkpoints del Lab:**
1. Sheet personalizado con 3 pestañas y datos propios de su trabajo
2. Plantilla Slides con marca propia + flujos duplicados y adaptados
3. Sistema propio validado end-to-end con datos reales

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Transferencia | Aplicar un patrón aprendido (Roberto) a un contexto nuevo (tu trabajo) |
| Personalización | Adaptar datos, marca, métricas y prompts a tu caso específico |
| Debug en Make | Usar "Run this module only" para aislar errores |
| Datos reales | Información verídica de tu trabajo (no simulada) |

**Anti-hype:**
- Tu sistema va a tener errores similares al modelo — nuevo caso, mismos tipos de fallos
- La habilidad no es que funcione perfecto, es saber CÓMO corregirlo
- Un sistema imperfecto para tu caso real vale más que uno perfecto de tutorial

**Dependencias:**
- **Requiere:** C05-C06 (sistema modelo completo + optimizado), Clase 1 (brief)
- **Habilita:** C08 (presentar sistema propio en vivo)

---

### Clase 8 (Cierre de Módulo y del Curso): Demo Day + ROI + Plan 30 días

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Presentar, cuantificar valor y proyectar (cierre del curso) |
| **Objetivo del Lab** | Presentar sistema en vivo + calcular ROI + definir plan 30 días |
| **Herramientas** | 0 nuevas |
| **Entregable** | Demo grabado + ROI documentado + plan 30 días + rúbricas de pares |

**Actividades del Lab (formato Demo Day):**
1. **Actividad 1 (60 min):** Demos en vivo — 5 min por estudiante con estructura PSDR (Problema / Solución / Demo en vivo / Resultado), rúbrica entre pares llenada.
2. **Actividad 2 (40 min):** Cada estudiante calcula su ROI (horas ahorradas × tarifa × 4 = mensual; × 12 = anual) + comparación grupal del mayor ROI.
3. **Actividad 3 (30 min):** Plan 30 días — listar 10 tareas repetitivas → aplicar 80/20 → 3 próximos agentes a construir → compromiso público con el grupo.

**Checkpoints del Lab:**
1. Demo en vivo de 5 min exitosa (todos presentan)
2. ROI calculado con números concretos
3. Plan 30 días escrito con 3 agentes identificados

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| PSDR | Problema + Solución + Demo + Resultado (estructura de 5 min) |
| ROI | Return on Investment — horas ahorradas × tarifa |
| Demo en vivo | Mostrar el sistema funcionando con datos reales, no con slides |
| Plan 80/20 | Identificar las 3 tareas que quitan 80% del tiempo |
| Quick-win | Automatización de alto impacto y baja dificultad |

**Dependencias:**
- **Requiere:** C07 (sistema propio funcionando)
- **Habilita:** Continuidad autónoma post-curso, ruta a AI 201/301

---

## Conexión con Módulo 1

### Lo que M1 estableció y M2 escaló

| M1 Estableció | M2 Escaló |
|---------------|-----------|
| Gem asistente con brief | Prompts de producción (chain-of-thought, few-shot, persona) |
| Sheet con 3 pestañas vacías | Sheet con datos reales llegando via IA + Historico acumulándose |
| Marcadores tipo 3 nombrados pero vacíos | Marcadores tipo 3 llenos con insights generados por Gemini |
| 2 flujos manuales sin IA | 2 flujos activos 24/7 con IA (instantáneo + scheduled) |
| Caso Roberto como referencia | Caso real del estudiante (C07) |
| "Aprender el patrón" | "Aplicar el patrón a mi trabajo" |

### Semillas de M1 que fructifican en M2

- C01 (brief) → C05 usa el brief como contexto del SystemPrompt de Gemini API
- C02 (columnas + rangos) → C05 los referencia desde HTTP/JSON sin depender de coordenadas
- C03 (marcadores tipo 3 nombrados) → C05 los rellena con prompts estructurados
- C04 (escenarios sin IA) → C05 inserta módulos HTTP en los mismos escenarios
- Tabla de parámetros (M1 entera) → C06 la usa para optimización; C07 la adapta al caso real

---

## Herramientas del Módulo

| Clase | Herramienta Nueva | Ya Conocida | Límite |
|-------|-------------------|-------------|--------|
| 5 | Gemini API + HTTP module en Make | Gem, Sheet, Slides, Make | 2 conceptos nuevos (API y HTTP) |
| 6 | (ninguna) | Todo el stack | 0 nuevas |
| 7 | (ninguna) | Todo el stack | 0 nuevas |
| 8 | (ninguna) | Todo el stack | 0 nuevas |

Respeta la regla `MAX_TWO_NEW_TOOLS` — de hecho, solo C05 introduce cosas nuevas; C06-C08 consolidan y aplican.

---

## Checklist de Verificación

Antes de aprobar este plan, verificar:

- [x] Las 4 competencias son medibles con verbos de acción
- [x] Cada clase tiene UN concepto principal claro
- [x] Los checkpoints son verificables
- [x] Las dependencias entre clases son explícitas
- [x] La clase 8 integra el trabajo de todo el curso
- [x] Hay conexión clara con M1 (semillas → frutos)
- [x] El glosario cubre todos los términos nuevos
- [x] Herramientas nuevas respetan el límite
- [x] C05 es explícitamente la bisagra del curso (único que introduce nuevas herramientas)
- [x] C07 tiene acompañamiento 1 a 1 previsto
- [x] C08 incluye formato Demo Day con ROI y plan 30 días
- [x] README.md está alineado con este plan
