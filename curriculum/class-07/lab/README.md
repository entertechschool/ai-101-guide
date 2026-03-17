# Lab 07: Mi Agente Real

## Objetivo

Construir un agente generativo desde cero que **analiza** input desordenado y **genera** un email profesional. A diferencia de C05-C06 donde el agente clasificaba, aquí encadenas 2 llamadas de IA: una que extrae estructura del caos, otra que produce output profesional.

> ⏱️ **Tiempo estimado:** 60 minutos

---

## Arquitectura: 2 IAs Encadenadas

```
Form v0 (textarea + campo extra + email)
    │
    ▼
Webhook (Make)
    │
    ▼
OpenRouter #1 — ANALIZAR
(input crudo → JSON estructurado)
    │
    ├──────────────────┐
    ▼                  ▼
Google Sheets      OpenRouter #2 — GENERAR
(registra log)     (JSON → email HTML profesional)
                       │
                       ▼
                   Gmail → envía al email del usuario
```

**5 módulos en Make:** Webhook + OpenRouter #1 + Google Sheets + OpenRouter #2 + Gmail

**¿Qué es nuevo?** En C05-C06, la IA clasificaba (URGENTE/CONSULTA/VENTA). Aquí, la primera IA **analiza** (extrae estructura) y la segunda IA **genera** (produce contenido profesional). Es el siguiente nivel: de clasificar a crear.

---

## Antes de empezar

| ✅ | Requisito |
|----|-----------|
| | Escenario elegido (ver siguiente sección) |
| | API key de OpenRouter funcionando (la misma de C05-C06) |
| | Claude abierto para personalizar SystemPrompts |

---

## Elige tu escenario

| # | Escenario | Input | Output (email) | Wow |
|---|-----------|-------|-----------------|-----|
| 1 | Clarificador de Ideas | Idea desordenada | Brief profesional con fortalezas, gaps y próximos pasos | "Escribí 3 líneas y me llegó un brief" |
| 2 | Procesador de Notas de Reunión | Garabatos, abreviaturas, frases sueltas | Acta ejecutiva con tabla de tareas y decisiones | "Pegué mis garabatos y me llegó un acta" |
| 3 | Generador de Feedback Profesional | Feedback crudo/emocional | Guía SBI con reformulaciones y tips de entrega | "Escribí mi frustración y me llegó una guía profesional" |
| 4 | Tu propio caso | Tu input real | Tu output profesional | Diseña con la plantilla del Apéndice |

> 💡 **¿No sabes cuál elegir?** Escenario 2 (Notas de Reunión) es el más universal — todos tenemos reuniones.

---

## Parte 1: Diseñar (10 min)

1. Abre [scenarios.md](scenarios.md) y encuentra tu escenario (o la plantilla para caso propio)
2. Lee los 2 SystemPrompts (OR#1 analítico + OR#2 generativo)
3. Personaliza con Claude (callback C03): pega ambos SystemPrompts y pide ajustes para tu rol, industria y contexto
4. **Caso propio (opción 4):** llena las 3 preguntas guía, verifica el checklist de viabilidad (mínimo 6/7), y diseña tus SystemPrompts con Claude

> ✅ **Checkpoint Parte 1:** 2 SystemPrompts listos — uno analítico (OR#1) y uno generativo (OR#2)

---

## Parte 2: Construir (40 min)

### 2.1 Crear form en v0 (8 min)

Abre v0.dev y crea un formulario con: textarea grande (tu input), campo extra según escenario, campo de email, div oculto para debug, botón de enviar, estilo profesional fondo oscuro.

| Escenario | textarea | Campo extra |
|-----------|----------|-------------|
| 1. Ideas | "Escribe tu idea aquí..." | — |
| 2. Reunión | "Pega tus notas aquí..." | input: "Contexto de la reunión" |
| 3. Feedback | "Escribe tu feedback aquí..." | select: Jefe/Par/Reporte directo |
| 4. Propio | Tu input | Tu campo extra |

Verifica que el form envía los datos como JSON al hacer submit (revisa el bloque debug).

### 2.2 Crear escenario en Make (5 min)

1. En Make, crea un **nuevo escenario** (no clonar C06 — esta es arquitectura diferente)
2. Agrega módulo **Webhook** → Custom webhook → Create → copia la URL
3. Haz un test: envía datos desde tu form → verifica que Make los recibe

### 2.3 Configurar OpenRouter #1 — ANALIZAR (7 min)

1. Agrega módulo **HTTP** → Make a Request
2. URL: `https://openrouter.ai/api/v1/chat/completions` | Method: POST
3. Headers: `Authorization: Bearer [tu API key]` + `Content-Type: application/json`
4. Body: modelo `google/gemini-2.0-flash-001`, system message con tu **SystemPrompt #1**, user message con `{{webhook.campo_textarea}} {{webhook.campo_extra}}`, **temperature: 0.3**
5. Parse response → sí
6. Verifica: envía un test → el output debe ser un JSON estructurado

> ⚠️ **Temperature 0.3** para OR#1 (análisis = precisión). Usaremos 0.7 para OR#2 (generación = creatividad).

### 2.4 Configurar Google Sheets (5 min)

1. Agrega módulo **Google Sheets** → Add a Row
2. Crea una hoja nueva con columnas según tu escenario:

| Escenario | Columnas |
|-----------|----------|
| 1. Ideas | timestamp, email, concepto_central, num_gaps, num_fortalezas |
| 2. Reunión | timestamp, email, contexto, num_decisiones, num_tareas, num_pendientes |
| 3. Feedback | timestamp, email, relacion, tipo_feedback, num_juicios |

3. Mapea los campos del JSON de OR#1 a las columnas
4. Verifica: envía test → fila aparece en Sheets

### 2.5 Configurar OpenRouter #2 — GENERAR (5 min)

1. Agrega otro módulo **HTTP** → Make a Request (misma config que OR#1)
2. Cambia: **SystemPrompt #2** (generativo), user message: `{{OR1.choices[0].message.content}}`, **temperature: 0.7**
3. Verifica: el output debe ser un email HTML formateado

### 2.6 Configurar Gmail (3 min)

1. Agrega módulo **Gmail** → Send an Email
2. To: `{{webhook.email}}`
3. Subject: según escenario ("Tu idea clarificada", "Acta de reunión", "Guía de feedback")
4. Content: `{{OR2.choices[0].message.content}}`
5. **Marcar "HTML"** en el formato del cuerpo

> ⚠️ **Error común:** Si el email llega como texto plano con tags HTML visibles, verifica que marcaste la opción HTML en Gmail.

### 2.7 Conectar form + smoke test (2 min)

1. Pega la URL del webhook en tu formulario v0
2. Deploy en v0 (click "Deploy")
3. Activa el escenario en Make (toggle ON)
4. Envía 1 mensaje de prueba desde el form
5. Verifica: email llega a tu correo + fila aparece en Sheets

> ✅ **Checkpoint Parte 2:** Form live en Vercel + email llega + Sheets registra

---

## Parte 3: Verificar (5 min)

### 3.1 Enviar 2 mensajes desde URL de Vercel (3 min)

1. Abre tu URL de Vercel (la URL pública de tu form)
2. Envía 2 mensajes diferentes — usa casos reales de tu trabajo
3. Verifica que ambos emails llegan y Sheets registra ambos

### 3.2 Verificar todo end-to-end (2 min)

| ✅ | Verificación |
|----|-------------|
| | Email llega con formato HTML profesional |
| | Google Sheets tiene al menos 2 registros |
| | URL de Vercel funciona públicamente |

> ✅ **Checkpoint Parte 3:** Agente funcionando end-to-end con 2 mensajes probados

---

## Entregable

1. **URL de Vercel** — form funcionando públicamente
2. **Screenshot de Make** — escenario con 5 módulos visibles
3. **Screenshot de Google Sheets** — con al menos 2 registros
4. **Screenshot del email recibido** — output generado por el agente
5. **SystemPrompts copiados** — OR#1 + OR#2 accesibles (para usar en C08)

**Formato:** Link directo (Vercel) + screenshots en Google Doc

---

## Bonus (opcional)

- Agrega CSS personalizado al email HTML (colores, logo, tipografía)
- Envía 5 mensajes variados y compara la calidad de los outputs
- Crea un segundo escenario en el mismo Make (duplica los módulos OR#1 + OR#2)
- Agrega un campo al form que cambie el "tono" del email generado (formal/casual)

> Ver [scenarios.md](scenarios.md) para los SystemPrompts y escenarios detallados (Escenarios 1-3 + plantilla para caso propio).
