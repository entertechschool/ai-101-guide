# Plan del Módulo 2: Superpoderes Aplicados + Portfolio

> Este documento define la arquitectura del módulo. Aprobar antes de crear clases.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Módulo** | 2 |
| **Título** | Superpoderes Aplicados + Portfolio |
| **Tema Central** | Escalar habilidades de M1 con automatización, personalización y storytelling profesional |
| **Clases** | 5 a 8 |
| **Pre-requisitos** | M1 completo (prompting, socio pensante, research, proyecto integrador) |

---

## Competencias del Módulo

Al finalizar el módulo, el estudiante podrá:

1. **Construir un agente IA funcional** - Crear un flujo automatizado en Make que usa IA para tomar decisiones (triage), no solo ejecutar reglas fijas
2. **Expandir un agente con lógica condicional y logging** - Agregar Router para branching, Google Sheets para registro, y Gmail para acción diferenciada
3. **Transferir el patrón agente a un caso real** - Aplicar la arquitectura de C05-C06 a un proceso genuino de su trabajo, clonando y adaptando el escenario
4. **Presentar y comunicar competencia IA** - Presentar su trabajo en 5 minutos, publicar en LinkedIn y definir un plan de desarrollo de 30 días

---

## Portfolio del Módulo

### Descripción

Durante las clases 5-8, el estudiante escala de "usuario intencional" (M1) a "profesional que integra IA en su día a día" (M2). El módulo tiene tres fases: construir un agente guiado (C05-C06), transferir a caso real (C07), y presentar + publicar (C08).

La diferencia fundamental con M1: en M1 el estudiante aprendió a USAR IA. En M2 aprende a hacer que la IA trabaje POR él (C05-C06), a APLICAR a su contexto real (C07), y a DEMOSTRAR su competencia profesionalmente (C08).

El portfolio se construye clase a clase en un Google Doc. No es un ejercicio académico — es evidencia profesional que el estudiante publica en LinkedIn y puede mostrar en entrevistas, evaluaciones o propuestas.

### Evolución por Clase

| Clase | Enfoque | Pieza del Portfolio al Finalizar |
|-------|---------|----------------------------------|
| 5 | Cerebro del agente (Form → Webhook → OpenRouter) | Form v0 + agente parcial en Make |
| 6 | Agente inteligente (Gmail + Router + Sheets) | 1 agente completo con branching + logging |
| 7 | Transferencia a caso real | Agente real funcionando + tabla resultados + mejora documentada |
| 8 | Presentación + futuro | Demo live + LinkedIn publicado + plan 30 días |

### Entregables del Módulo

Al finalizar M2, el estudiante tiene:
- 1 agente IA completo en Make (triage con Router + Gmail + Google Sheets)
- 1 agente IA para caso real de trabajo (transferencia C07)
- 1 caso de éxito publicado en LinkedIn (métricas reales)
- 1 plan de desarrollo de 30 días con 3 quick-wins

---

## Arco Narrativo del Módulo

```
C05: "La IA trabaja POR ti"        → Construir el cerebro del agente
C06: "La IA decide DIFERENTE"      → De flujo lineal a agente inteligente
C07: "Ahora hazlo para TI"         → Transferencia a caso real
C08: "Demuestra y planifica"       → Demo live + LinkedIn + futuro
```

### Diseño Híbrido

Las clases 5 y 6 construyen un agente completo en dos partes (C05 = cerebro, C06 = cuerpo inteligente) usando PetShop Express como caso guiado. La clase 7 es la prueba real: el estudiante toma el patrón y lo aplica a un proceso de SU trabajo. La clase 8 es la culminación: presenta su agente en vivo, publica en LinkedIn y planifica.

---

## Arquitectura de Clases

### Clase 5: Tu Primer Agente IA

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Agente = automatización que DECIDE (no solo ejecuta) |
| **Objetivo del Lab** | Construir el cerebro del agente: Form v0 → Webhook Make → OpenRouter/Grok |
| **Herramientas** | Make (nueva), OpenRouter + Grok Free (nueva), v0 (nueva — vehículo pedagógico), Gemini (ya conocida de C04) |
| **Entregable** | Parcial — Form v0 + agente en Make (2 módulos) + primer test en Make History. Se completa en C06 |

> **Nota MAX_TWO_NEW_TOOLS:** Esta clase introduce 3 herramientas nuevas (Make, v0, OpenRouter/Grok). La regla se flexibiliza porque v0 es un vehículo pedagógico que refuerza técnicas de M1 (Few-shot de C02, Socio pensante de C03), no una herramienta central del curso.

> **Descubrimiento de clase real:** Los estudiantes usaron Gemini como scaffolding para el prompt de v0, y descubrieron agregar un bloque debug al form (muestra respuesta del servidor + botón reintentar). Se incorporó al lab.

**Conexión con M1:** Evolución directa de C02. En C02 el estudiante clasificó mensajes manualmente con RICE + Few-shot. En C05 ese mismo proceso comienza a automatizarse — el prompt de C02 se convierte en el SystemPrompt del agente.

**Refuerzo pedagógico de M1:**

| Técnica M1 | Refuerzo en C05 |
|------------|-----------------|
| Few-shot / Ejemplo (C02) | Wireframe adjunto al prompt de v0 |
| Socio pensante (C03) | Gemini como scaffolding del prompt de v0 |
| System prompt (C01) | SystemPrompt en OpenRouter |
| RICE (C02) | Estructura del UserPrompt |

**Arquitectura:**
```
Form (v0.app + debug) → Webhook (Make) → OpenRouter (SystemPrompt + UserPrompt)
```

**Enfoque del Lab:** Template base (2 módulos) + personalización
- Scaffolding con Gemini para definir el prompt de v0
- Crea formulario con v0 (Few-shot + bloque debug)
- Clona template en Make: Webhook → OpenRouter
- Configura API Key de OpenRouter (paso explícito con troubleshooting)
- Personaliza SystemPrompt (rol + reglas + categorías) y UserPrompt (mapeo de datos del form)
- Primer test: enviar mensajes y ver clasificación en Make History

**Checkpoints del Lab:**
1. Formulario v0 deployado con URL pública y bloque debug
2. API Key de OpenRouter conectada (checkmark verde)
3. SystemPrompt personalizado, form conectado al webhook
4. Primer test exitoso — clasificación visible en Make History

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Agente IA | Automatización que usa IA para tomar decisiones, no solo seguir reglas |
| Make | Plataforma visual de automatización no-code (antes Integromat) |
| Trigger | Evento que inicia un flujo automatizado (datos entrantes, webhook, schedule) |
| OpenRouter | Plataforma que da acceso a múltiples modelos de IA con una sola API |
| Grok | Modelo de IA de xAI, disponible gratis vía OpenRouter |
| Webhook | URL que recibe datos automáticamente cuando ocurre un evento |
| v0 | Herramienta de Vercel que genera interfaces web desde un prompt |
| Bloque debug | Panel en el formulario que muestra respuesta del servidor + reintentar |
| SystemPrompt | Instrucciones permanentes que definen el ROL y REGLAS del agente |
| UserPrompt | Datos específicos de cada mensaje que el agente procesa |

**Anti-hype:**
- Un agente es tan bueno como su SystemPrompt — basura entra, basura sale
- Grok Free tiene límites de uso y puede ser más lento en horas pico
- La IA puede clasificar mal mensajes ambiguos — siempre necesitas supervisión humana
- Automatizar un proceso malo solo produce errores más rápido

**Dependencias:**
- **Requiere:** C02 (RICE, few-shot, triage), C03 (socio pensante), C04 (experiencia con múltiples herramientas)
- **Habilita:** C06 (completar agente con Gmail + Router + Sheets)

---

### Clase 6: Tu Agente Inteligente

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | De flujo lineal a agente inteligente (branching + logging) |
| **Objetivo del Lab** | Completar agente (Gmail) + expandir con Router (3 rutas) + Google Sheets (logging) + battle de agentes |
| **Herramientas** | Google Sheets en Make (nueva), Router + Gmail = módulos nativos de Make (continuación C05) |
| **Entregable** | Agente completo con branching + logging + resultados battle + análisis crítico |

**Conexión con C05:** C05 construyó el cerebro (Form → Webhook → OpenRouter). C06 lo completa: agrega Gmail (manos), Router (inteligencia), Google Sheets (memoria). El entregable de C05 se completa en C06.

**Distinción clave:**
```
C05 (lineal):    Form → Webhook → OpenRouter → ver en Make History
C06 (branching): Form → Webhook → OpenRouter → Router → [3 rutas Gmail] + Sheets
```

**Lo que construye:**

1. **Completar agente** — Agregar Gmail para acción end-to-end (momento WOW)
2. **Router con 3 rutas** — URGENTE (Gmail rojo), CONSULTA (Gmail normal), VENTA (Gmail verde)
3. **Google Sheets** — Logging de cada decisión (timestamp + datos + categoría + acción)
4. **Battle de agentes** — 5 mensajes PetShop Express, votan mejor SystemPrompt

**Checkpoints del Lab:**
1. Gmail conectado — emails con clasificación (momento WOW)
2. Router con 3 rutas funcionando (Filters correctos)
3. Google Sheets registrando datos automáticamente
4. Battle completado — 5 mensajes clasificados, votación del mejor SystemPrompt

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Router | Módulo de Make que divide un flujo en múltiples rutas condicionales |
| Filter | Condición que determina cuándo se activa una ruta del Router |
| Branching | Patrón donde un flujo se divide en múltiples caminos según condiciones |
| Logging | Registrar cada acción/decisión del agente en un lugar persistente |
| Google Sheets (en Make) | Módulo que permite agregar filas a una hoja de cálculo automáticamente |

**Anti-hype:**
- Router solo es tan bueno como los Filters — si el SystemPrompt produce categorías inconsistentes, el Router falla
- Google Sheets no es un dashboard automático — registra datos, pero analizarlos es tu trabajo
- Más módulos = más puntos de falla — cada conexión nueva puede romperse
- El battle demuestra que el modelo no importa tanto como el SystemPrompt

**Battle (COMPETITIVE_COLLABORATION para M2):**
- Todos envían los mismos 5 mensajes de PetShop Express
- Comparan resultados en Google Sheets
- Votan el mejor SystemPrompt
- Lección: el prompt define la calidad, no el modelo

**Dependencias:**
- **Requiere:** C05 (agente cerebro: Form + Webhook + OpenRouter)
- **Habilita:** C07 (transferencia — agente completo como base para caso real)

---

### Clase 7: Mi Agente Real

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Transferencia — aplicar el patrón agente a tu caso real de trabajo |
| **Objetivo del Lab** | Diseñar caso real + clonar y adaptar escenario C06 + probar con datos reales |
| **Herramientas** | 0 nuevas (Make, OpenRouter, Gmail, Router, Sheets, Claude — todas de C05-C06) |
| **Entregable** | Agente real funcionando + tabla resultados (esperado vs real) + mejora documentada |

**Concepto clave:** No es aprender herramientas nuevas. Es demostrar que puedes APLICAR lo aprendido a un contexto nuevo. PetShop fue el entrenamiento — ahora construyes para TU trabajo.

**Insight:** "La arquitectura se queda. El cerebro cambia."
- Qué cambia: SystemPrompt, categorías, formulario, emails
- Qué se queda: Webhook → OpenRouter → Router → Gmail → Sheets

**Lo que construye:**

1. **Diseño del caso** (con tabla de 6 arquetipos por industria)
   - Elegir proceso real de trabajo que involucre clasificar/priorizar/decidir
   - Definir 3 categorías + reglas + acciones
   - Escribir SystemPrompt con Claude como socio pensante (callback C03)

2. **Agente adaptado** (clonando escenario C06)
   - Clonar escenario en Make (Export/Import Blueprint)
   - Nuevo formulario v0 con campos de su caso (scaffolding Gemini, callback C05)
   - Adaptar módulo por módulo: OpenRouter, Router Filters, Gmail ×3, Sheets

3. **Prueba + iteración** con datos reales
   - 5 mensajes reales desde su formulario
   - Tabla de resultados: esperado vs real
   - Iterar SystemPrompt hasta mejorar precisión

**Checkpoints del Lab:**
1. Caso diseñado con 3 categorías + reglas + SystemPrompt
2. Escenario clonado + formulario v0 nuevo deployado
3. Módulos adaptados + form conectado al webhook
4. 5 mensajes probados + al menos 1 mejora documentada

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Transferencia | Aplicar un patrón aprendido (PetShop) a un contexto nuevo (tu trabajo) |
| Caso de uso | Proceso real de tu trabajo que el agente va a resolver |
| Iteración | Ciclo de probar → encontrar errores → mejorar SystemPrompt → re-probar |
| Arquetipos | Patrones comunes de casos de triage por industria |
| Clonación de escenario | Duplicar un escenario en Make como base para uno nuevo |

**Anti-hype:**
- Tu agente va a tener las mismas fallas que PetShop — nuevo caso, mismos tipos de errores
- La habilidad no es que funcione perfecto — es saber CÓMO corregirlo
- Un agente imperfecto para tu caso real vale más que uno perfecto de tutorial
- Iterar con datos reales es lo que separa un prototipo de algo útil

**Dependencias:**
- **Requiere:** C05-C06 (agente completo PetShop), C03 (socio pensante para SystemPrompt), C02 (RICE para diseño de reglas)
- **Habilita:** C08 (presentar agente real en vivo + publicar en LinkedIn)

---

### Clase 8 (Cierre de Módulo): Demo Day + El Futuro

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Presentar, publicar y planificar (cierre del ciclo completo) |
| **Objetivo del Lab** | Test M2 + presentar agente en vivo + publicar LinkedIn + plan 30 días |
| **Herramientas** | 0 nuevas (Make, LinkedIn, Claude — todas conocidas) |
| **Entregable** | Presentación completada + LinkedIn publicado + plan 30 días con 3 quick-wins |
| **Test Diagnóstico** | 8 preguntas (15 min) - no afecta calificación |

**Estructura de la clase (3 actos: PRESENTAR, PUBLICAR, PLANIFICAR):**

1. **Test M2** — 8 preguntas, 15 min, diagnóstico (no afecta calificación)
2. **Pulir + peer review** — Últimos ajustes + compañero prueba tu agente
3. **Presentaciones** — 5 min por persona, DEMO EN VIVO (no slides)
   ```
   Mi problema (30 seg)     → "En mi trabajo, X me costaba Y"
   Mi agente (2 min)        → Mostrar Make + explicar categorías
   Demo en vivo (1.5 min)   → Alguien del PÚBLICO envía mensaje al agente
   Lo que aprendí (1 min)   → 1 error corregido + 1 limitación honesta
   ```
4. **Feedback de pares** — 1 fortaleza + 1 sugerencia por presentación
5. **Publicar LinkedIn** — Todos publican juntos "3... 2... 1... PUBLICAR!"
6. **Roadmap 30 días** — Con Claude, 3 quick-wins para esta semana
7. **Cierre** — Del 95% al 5%, pathway AI 201/301

**Checkpoints del Lab:**
1. Test M2 completado (15 min)
2. Agente probado por un par (peer review)
3. Presentación con demo live completada + feedback recibido
4. LinkedIn post publicado + plan de 30 días con 3 quick-wins

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Demo Day | Sesión donde cada estudiante muestra su agente funcionando en vivo |
| Feedback de pares | Evaluación constructiva: 1 fortaleza + 1 sugerencia |
| Quick-win | Acción específica de alto impacto y baja dificultad para esta semana |
| Roadmap | Plan de 30 días con acciones concretas |
| Accountability | Compromiso público que motiva a cumplir (publicar juntos) |

**Anti-hype:**
- Publicar en LinkedIn no te hace experto — la práctica continua sí
- 4 semanas es el inicio, no el final — el plan de 30 días es lo que consolida el cambio
- Las herramientas van a cambiar; las habilidades de pensamiento crítico con IA no
- Tu agente necesita supervisión continua — ninguna IA reemplaza el criterio humano
- El mejor indicador de éxito: ¿sigues usando lo que aprendiste 30 días después?

**Dependencias:**
- **Requiere:** C07 (agente real funcionando, probado, con 5 mensajes de prueba)
- **Habilita:** Continuidad autónoma del estudiante, pathway a AI 201/301

---

## Conexión con Módulo 1

### Lo que M1 establece y M2 escala

| M1 Establece | M2 Escala |
|--------------|-----------|
| Triage manual con RICE (C02) | Triage automatizado con agente (C05) |
| Claude Projects con instrucciones (C03) | Agente inteligente con branching + logging (C06) |
| Gem de Gemini configurado (C04) | Agente real para tu caso de trabajo (C07) |
| Proyecto integrador individual (C04) | Demo live + LinkedIn + plan futuro (C08) |
| "Sé usar IA" | "La IA trabaja para mí y puedo demostrarlo" |

### Semillas plantadas en M1 para M2

- C02 (triage manual) → C05-C06 (mismo caso, ahora automatizado con branching)
- C03 (Claude Projects) → C05 (SystemPrompt del agente)
- C04 (Gems, múltiples herramientas) → C05-C06 (nuevas herramientas con confianza)
- C04 (proyecto con métricas) → C08 (caso de éxito con métricas reales)
- C05-C06 (agente PetShop) → C07 (transferencia a caso real)

---

## Herramientas del Módulo

| Clase | Herramienta Nueva | Ya Conocida | Límite |
|-------|-------------------|-------------|--------|
| 5 | Make, OpenRouter/Grok Free, v0 (vehículo pedagógico) | Gemini (C04) | 3 nuevas* |
| 6 | Google Sheets en Make | Router + Gmail (módulos nativos Make) | 1 nueva |
| 7 | (ninguna) | Make, OpenRouter, Claude, Gemini (todas de C05-C06) | 0 nuevas |
| 8 | (ninguna) | Make, LinkedIn, Claude | 0 nuevas |

*C05 flexibiliza la regla MAX_TWO_NEW_TOOLS: v0 es vehículo pedagógico que refuerza M1, no herramienta central del curso. Las demás clases dentro del límite de 2.

---

## Checklist de Verificación

Antes de aprobar este plan, verificar:

- [ ] Las 4 competencias son medibles con verbos de acción
- [ ] Cada clase tiene UN concepto principal claro
- [ ] Los checkpoints son verificables (screenshot, documento, link)
- [ ] Las dependencias entre clases son explícitas
- [ ] La clase 8 integra el trabajo de todo el curso (no solo M2)
- [ ] Hay conexión clara con M1 (semillas → frutos)
- [ ] El glosario cubre todos los términos nuevos
- [ ] Herramientas nuevas respetan el límite de 2 por clase
- [ ] C05 y C06 construyen un agente completo en dos partes
- [ ] Battle de agentes incluido en C06 (COMPETITIVE_COLLABORATION M2)
- [ ] README.md está alineado con este plan
