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
3. **Documentar un caso de éxito profesional** - Convertir su mejor logro del curso en un caso de éxito con métricas antes/después, armado en portfolio Notion
4. **Presentar y comunicar competencia IA** - Presentar su trabajo en 5 minutos, publicar en LinkedIn y definir un plan de desarrollo de 30 días

---

## Portfolio del Módulo

### Descripción

Durante las clases 5-8, el estudiante escala de "usuario intencional" (M1) a "profesional que integra IA en su día a día" (M2). El módulo tiene dos fases: primero adquiere dos superpoderes nuevos (agente cerebro + agente inteligente), luego documenta y presenta toda su transformación.

La diferencia fundamental con M1: en M1 el estudiante aprendió a USAR IA. En M2 aprende a hacer que la IA trabaje POR él (C05-C06), y a DEMOSTRAR su competencia profesionalmente (C07-C08).

El portfolio completo en Notion integra las 7 clases del curso. No es un ejercicio académico — es evidencia profesional que el estudiante publica en LinkedIn y puede mostrar en entrevistas, evaluaciones o propuestas.

### Evolución por Clase

| Clase | Enfoque | Pieza del Portfolio al Finalizar |
|-------|---------|----------------------------------|
| 5 | Cerebro del agente (Form → Webhook → OpenRouter) | Form v0 + agente parcial en Make |
| 6 | Agente inteligente (Gmail + Router + Sheets) | 1 agente completo con branching + logging |
| 7 | Storytelling + portfolio | Portfolio completo en Notion + caso de éxito + draft LinkedIn |
| 8 | Presentación + futuro | Presentación en vivo + LinkedIn publicado + plan 30 días |

### Entregables del Módulo

Al finalizar M2, el estudiante tiene:
- 1 agente IA completo en Make (triage con Router + Gmail + Google Sheets)
- 1 portfolio completo en Notion (piezas de C01-C07)
- 1 caso de éxito publicado en LinkedIn (métricas reales)
- 1 plan de desarrollo de 30 días con 3 quick-wins

---

## Arco Narrativo del Módulo

```
C05: "La IA trabaja POR ti"        → Construir el cerebro del agente
C06: "La IA decide DIFERENTE"      → De flujo lineal a agente inteligente
C07: "Demuestra lo que lograste"   → Storytelling + portfolio
C08: "Comparte y planifica"        → Presentación + futuro
```

### Diseño Híbrido

Las clases 5 y 6 construyen un agente completo en dos partes (C05 = cerebro, C06 = cuerpo inteligente). La clase 7 integra TODO el curso: el estudiante elige su MEJOR pieza (de cualquier clase, M1 o M2) y la convierte en caso de éxito publicable. La clase 8 es la culminación: presenta, publica y planifica.

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
- **Habilita:** C07 (pieza de portfolio — agente completo como evidencia)

---

### Clase 7: Portfolio + Caso de Éxito

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Storytelling de competencia IA (documentar y narrar tu transformación) |
| **Objetivo del Lab** | Armar portfolio en Notion + escribir caso de éxito + draft LinkedIn |
| **Herramientas** | Notion (nueva), Claude (storytelling) |
| **Entregable** | Portfolio en Notion + caso de éxito documentado + draft de LinkedIn post |

**Concepto clave:** No es "aprender Notion". Es aprender a DOCUMENTAR Y NARRAR tu transformación con IA. Notion es el vehículo, el storytelling es la habilidad.

**Lo que construye:**

1. **Portfolio en Notion** (template esqueleto)
   - Estructura base proporcionada, estudiante personaliza
   - Recopila piezas de C01-C06 (screenshots, frameworks, agente, resultados)
   - Cada sección muestra una habilidad demostrable

2. **Caso de éxito** (la MEJOR pieza del curso)
   - Elige de cualquier clase (M1 o M2) — la que tenga mejor antes/después
   - Documenta: problema → qué hizo → resultado → métricas
   - Escribe con ayuda de Claude como editor de storytelling

3. **LinkedIn post draft** (formato sugerido)
   ```
   Hook (1 línea impactante)
   Problema (2-3 líneas)
   Qué hice (2-3 líneas)
   Resultado (1-2 líneas con métrica)
   Takeaway (1 línea)
   CTA (opcional)
   ```

4. **Preparar presentación** de 5 min para C08

**Checkpoints del Lab:**
1. Portfolio en Notion armado con piezas de al menos 5 clases (C01-C06)
2. Caso de éxito completo (problema + solución + métricas antes/después)
3. LinkedIn post en draft listo para publicar + presentación preparada

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Notion | Herramienta de productividad para documentación, bases de datos y portfolio |
| Caso de éxito | Narrativa estructurada que demuestra resultado medible con antes/después |
| Storytelling | Arte de contar una historia que conecta, persuade y demuestra competencia |
| Portfolio | Colección curada de evidencia profesional que demuestra habilidades |
| Hook | Primera línea de un post diseñada para captar atención inmediata |

**Anti-hype:**
- Un portfolio bonito sin métricas reales no impresiona a nadie
- Claude puede ayudarte a escribir el caso, pero las métricas tienen que ser REALES
- LinkedIn no es magia — el post funciona si el contenido es genuino
- "Uso IA" no es diferenciador. "Resolví X con IA y ahorré Y horas" sí lo es

**Dependencias:**
- **Requiere:** C01-C06 (todas las piezas del portfolio), habilidades de escritura con IA (C03)
- **Habilita:** C08 (presentación lista, LinkedIn listo para publicar)

---

### Clase 8 (Cierre de Módulo): Demo Day + El Futuro

| Aspecto | Detalle |
|---------|---------|
| **Concepto Principal** | Presentar, publicar y planificar (cierre del ciclo completo) |
| **Objetivo del Lab** | Presentar portfolio, publicar LinkedIn en vivo, crear plan 30 días |
| **Herramientas** | Notion (presentación), LinkedIn (publicación), Claude (roadmap) |
| **Entregable** | Presentación completada + LinkedIn publicado + plan 30 días con 3 quick-wins |
| **Test Diagnóstico** | 8 preguntas (15 min) - no afecta calificación |

**Estructura de la clase:**

1. **Pulir presentación** — Últimos ajustes al portfolio y presentación en Notion
2. **Presentaciones** — 5 min por estudiante desde su portfolio en Notion
   ```
   El problema (30 seg)    → "En mi trabajo, [X] me costaba [Y]"
   Qué hice (2 min)        → Herramienta/técnica que aplicó
   El resultado (1 min)     → Antes/después con métricas
   Lo que aprendí (1 min)   → Insight personal, limitaciones encontradas
   Qué sigue (30 seg)      → Sus próximos 3 quick-wins
   ```
3. **Feedback de pares** — Cada estudiante recibe de cada compañero:
   - 1 fortaleza específica
   - 1 oportunidad de mejora
4. **Publicar LinkedIn** — Todos publican su post juntos, en vivo (accountability grupal)
5. **Roadmap personal** — Template con 3 quick-wins para los próximos 30 días
6. **Cierre** — Preview de AI 201/301, certificado, celebración

**Checkpoints del Lab:**
1. Presentación completada (5 min, desde Notion)
2. Feedback dado y recibido de todos los compañeros
3. LinkedIn post publicado + plan de 30 días con 3 quick-wins definidos

**Glosario de la Clase:**

| Término | Definición breve |
|---------|------------------|
| Demo Day | Sesión de presentaciones donde cada estudiante muestra su mejor trabajo |
| Feedback de pares | Evaluación entre compañeros para mejorar con perspectivas diversas |
| Quick-win | Acción específica de alto impacto y baja dificultad que puedes ejecutar esta semana |
| Roadmap | Plan con hitos claros y acciones concretas para desarrollo futuro |

**Anti-hype:**
- Publicar en LinkedIn no te hace experto — la práctica continua sí
- 4 semanas es el inicio, no el final — el plan de 30 días es lo que consolida el cambio
- Las herramientas van a cambiar; las habilidades de pensamiento crítico con IA no
- El mejor indicador de éxito: ¿sigues usando lo que aprendiste 30 días después?

**Dependencias:**
- **Requiere:** C07 (portfolio listo, caso de éxito escrito, LinkedIn draft)
- **Habilita:** Continuidad autónoma del estudiante, pathway a AI 201/301

---

## Conexión con Módulo 1

### Lo que M1 establece y M2 escala

| M1 Establece | M2 Escala |
|--------------|-----------|
| Triage manual con RICE (C02) | Triage automatizado con agente (C05) |
| Claude Projects con instrucciones (C03) | Agente inteligente con branching + logging (C06) |
| Gem de Gemini configurado (C04) | Portfolio completo con caso de éxito publicable (C07) |
| Proyecto integrador individual (C04) | Presentación pública + LinkedIn + plan futuro (C08) |
| "Sé usar IA" | "La IA trabaja para mí y puedo demostrarlo" |

### Semillas plantadas en M1 para M2

- C02 (triage manual) → C05-C06 (mismo caso, ahora automatizado con branching)
- C03 (Claude Projects) → C05 (SystemPrompt del agente)
- C04 (Gems, múltiples herramientas) → C05-C06 (nuevas herramientas con confianza)
- C04 (proyecto con métricas) → C07 (caso de éxito con storytelling)
- Todos los entregables M1 → C07 (piezas del portfolio)

---

## Herramientas del Módulo

| Clase | Herramienta Nueva | Ya Conocida | Límite |
|-------|-------------------|-------------|--------|
| 5 | Make, OpenRouter/Grok Free, v0 (vehículo pedagógico) | Gemini (C04) | 3 nuevas* |
| 6 | Google Sheets en Make | Router + Gmail (módulos nativos Make) | 1 nueva |
| 7 | Notion | Claude (storytelling) | 1 nueva |
| 8 | (ninguna) | Notion, LinkedIn, Claude | 0 nuevas |

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
