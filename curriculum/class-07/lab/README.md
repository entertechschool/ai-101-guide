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

### Si elegiste un escenario predefinido (1, 2 o 3):

1. Ve al **Apéndice** de este lab y encuentra tu escenario
2. Lee los 2 SystemPrompts (OR#1 analítico + OR#2 generativo)
3. Personaliza con Claude (callback C03):

```
Tengo estos 2 SystemPrompts para mi agente [nombre del escenario].
[Pega ambos SystemPrompts]

Quiero personalizarlos para mi contexto:
- Mi rol: [tu rol]
- Mi industria: [tu industria]
- Detalle específico: [algo que quieras agregar]

¿Qué ajustes recomiendas? Hazme preguntas antes de modificar.
```

### Si elegiste caso propio (opción 4):

1. Ve al **Apéndice: Plantilla para caso propio**
2. Llena las 3 preguntas guía
3. Verifica con el checklist de viabilidad (mínimo 6 de 7 criterios)
4. Diseña tus 2 SystemPrompts con Claude:

```
Necesito diseñar 2 SystemPrompts encadenados para un agente.

Mi caso: [descripción]
Input del usuario: [qué va a escribir]
Output deseado: [qué email debería recibir]

SystemPrompt #1 debe ANALIZAR el input y producir un JSON estructurado.
SystemPrompt #2 debe tomar ese JSON y GENERAR un email HTML profesional.

Hazme preguntas antes de escribir los SystemPrompts.
```

> ✅ **Checkpoint Parte 1:** 2 SystemPrompts listos — uno analítico (OR#1) y uno generativo (OR#2)

---

## Parte 2: Construir (40 min)

### 2.1 Crear form en v0 (8 min)

Abre v0.dev y crea un formulario con este prompt:

```
Crea un formulario minimalista con:
- Un textarea grande para [describe tu input según escenario]
- [Campo extra según escenario: input texto o select]
- Un campo de email
- Un div oculto para mostrar respuestas del servidor (id="debug")
- Botón de enviar
- Estilo profesional, fondo oscuro
```

**Campos por escenario:**

| Escenario | textarea | Campo extra | email |
|-----------|----------|-------------|-------|
| 1. Ideas | "Escribe tu idea aquí..." | — | email |
| 2. Reunión | "Pega tus notas aquí..." | input: "Contexto de la reunión" | email |
| 3. Feedback | "Escribe tu feedback aquí..." | select: Jefe/Par/Reporte directo | email |
| 4. Propio | Tu input | Tu campo extra | email |

Verifica que el form envía los datos como JSON al hacer submit (revisa el bloque debug).

### 2.2 Crear escenario en Make (5 min)

1. En Make, crea un **nuevo escenario** (no clonar C06 — esta es arquitectura diferente)
2. Agrega módulo **Webhook** → Custom webhook → Create → copia la URL
3. Haz un test: envía datos desde tu form → verifica que Make los recibe

### 2.3 Configurar OpenRouter #1 — ANALIZAR (7 min)

1. Agrega módulo **HTTP** → Make a Request (o OpenRouter si tienes el módulo)
2. URL: `https://openrouter.ai/api/v1/chat/completions`
3. Method: POST
4. Headers:
   - `Authorization`: `Bearer [tu API key]`
   - `Content-Type`: `application/json`
5. Body (JSON):

```json
{
  "model": "google/gemini-2.0-flash-001",
  "messages": [
    {
      "role": "system",
      "content": "[TU SYSTEMPROMPT #1 — ANALIZAR]"
    },
    {
      "role": "user",
      "content": "{{webhook.campo_textarea}} {{webhook.campo_extra}}"
    }
  ],
  "temperature": 0.3
}
```

6. Parse response → sí
7. Verifica: envía un test → el output debe ser un JSON estructurado

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

1. Agrega otro módulo **HTTP** → Make a Request
2. Misma configuración que OR#1 pero con:
   - **SystemPrompt #2** (generativo)
   - **UserPrompt**: el JSON completo que OR#1 produjo
   - **Temperature: 0.7** (más creativo para generar contenido)

```json
{
  "model": "google/gemini-2.0-flash-001",
  "messages": [
    {
      "role": "system",
      "content": "[TU SYSTEMPROMPT #2 — GENERAR]"
    },
    {
      "role": "user",
      "content": "{{OR1.choices[0].message.content}}"
    }
  ],
  "temperature": 0.7
}
```

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

---

## Apéndice: Escenarios Detallados

### Escenario 1: Clarificador de Ideas

**Contexto:** Tienes una idea para un proyecto, producto o propuesta pero está desordenada en tu cabeza. Escribes lo que se te ocurre y el agente te devuelve un brief profesional.

**Form:** textarea (idea) + email

**SystemPrompt OR#1 — Analizar:**

```
Eres un analista de ideas de negocio. Tu trabajo es tomar ideas desordenadas y extraer estructura.

INSTRUCCIONES:
1. Lee el texto del usuario (puede ser desordenado, con errores, incompleto)
2. Identifica el concepto central en 1 oración
3. Lista las fortalezas de la idea (máximo 3)
4. Lista los gaps o preguntas sin responder (máximo 3)
5. Identifica el público objetivo probable
6. Evalúa la claridad del 1 al 5

FORMATO DE SALIDA (JSON estricto):
{
  "concepto_central": "string",
  "fortalezas": ["string", "string", "string"],
  "gaps": ["string", "string", "string"],
  "publico_objetivo": "string",
  "claridad": number,
  "resumen_ejecutivo": "string (2-3 oraciones)"
}

REGLAS:
- Si el texto es muy corto (menos de 10 palabras), devuelve claridad: 1 y en gaps indica "Necesita más contexto"
- No inventes información que no esté en el texto
- Los gaps deben ser preguntas específicas, no genéricas
- Responde SOLO con el JSON, sin texto adicional
```

**SystemPrompt OR#2 — Generar:**

```
Eres un consultor de innovación que escribe briefs profesionales por email.

INSTRUCCIONES:
Recibirás un JSON con el análisis de una idea. Genera un email HTML profesional que incluya:

1. Saludo breve y empático
2. Sección "Tu idea en una línea" — el concepto central reformulado de forma clara
3. Sección "Lo que funciona" — las fortalezas como bullet points con ícono ✅
4. Sección "Preguntas para resolver" — los gaps como preguntas accionables con ícono ❓
5. Sección "Público objetivo" — a quién le habla esta idea
6. Sección "Próximos pasos" — 3 acciones concretas para avanzar esta semana
7. Cierre motivacional breve

FORMATO:
- Email HTML con estilos inline
- Usa colores profesionales: fondo #f9f9f9, headers #2c3e50, accents #3498db
- Párrafos cortos, bullet points, negritas estratégicas
- Tono: profesional pero cercano, como un mentor
- NO incluyas "Estimado/a" — usa "Hola,"

REGLAS:
- Si la claridad es 1-2, el email debe enfocarse en las preguntas para resolver
- Si la claridad es 4-5, el email debe enfocarse en próximos pasos
- Máximo 400 palabras
```

**Mensajes de prueba:**

1. *"tengo una idea para una app que conecte freelancers con empresas pero diferente a upwork porque sería solo para latam y tendría un sistema de mentoría incluido no sé si cobrar por suscripción o por transacción"*
2. *"quiero hacer un podcast sobre tecnología para gente no técnica algo así como explicar IA y crypto sin jerga"*
3. *"negocio de comida saludable delivery pero solo almuerzos para oficinas"*

---

### Escenario 2: Procesador de Notas de Reunión

**Contexto:** Después de una reunión tienes notas desordenadas: abreviaturas, frases sueltas, ideas a medias. El agente extrae decisiones, tareas y pendientes, y te envía un acta ejecutiva profesional.

**Form:** textarea (notas) + input texto (contexto de la reunión) + email

**SystemPrompt OR#1 — Analizar:**

```
Eres un asistente ejecutivo experto en procesar notas de reunión desordenadas.

INSTRUCCIONES:
1. Lee las notas del usuario (pueden tener abreviaturas, errores, frases incompletas)
2. Lee el contexto de la reunión proporcionado
3. Extrae todas las decisiones tomadas
4. Extrae todas las tareas con responsable y plazo (si se mencionan)
5. Identifica temas que quedaron pendientes (sin decisión)
6. Detecta gaps: información que falta o contradicciones

FORMATO DE SALIDA (JSON estricto):
{
  "contexto_reunion": "string",
  "decisiones": [
    {"decision": "string", "responsable": "string o 'No especificado'"}
  ],
  "tareas": [
    {"tarea": "string", "responsable": "string o 'No especificado'", "plazo": "string o 'Sin plazo'"}
  ],
  "pendientes": ["string"],
  "gaps": ["string"],
  "num_decisiones": number,
  "num_tareas": number,
  "num_pendientes": number
}

REGLAS:
- Si no hay responsable claro, pon "No especificado" (NO inventes nombres)
- Si no hay plazo, pon "Sin plazo"
- Distingue decisión (algo que se acordó) de tarea (algo que alguien debe hacer)
- Los gaps deben ser específicos: "No se definió quién aprueba el presupuesto"
- Responde SOLO con el JSON, sin texto adicional
```

**SystemPrompt OR#2 — Generar:**

```
Eres un asistente ejecutivo que escribe actas de reunión profesionales por email.

INSTRUCCIONES:
Recibirás un JSON con el análisis de notas de reunión. Genera un email HTML con formato de "Acta Ejecutiva" que incluya:

1. Header: "Acta Ejecutiva" + contexto de la reunión + fecha de hoy
2. Sección "Decisiones" — tabla con columnas: Decisión | Responsable
3. Sección "Tareas" — tabla con columnas: Tarea | Responsable | Plazo
4. Sección "Temas Pendientes" — lista con ícono ⏳
5. Sección "Gaps Detectados" — lista con ícono ⚠️ (solo si hay gaps)
6. Resumen: "X decisiones, Y tareas asignadas, Z temas pendientes"

FORMATO:
- Email HTML con estilos inline
- Tablas con bordes claros, headers en #2c3e50, filas alternas en #f2f2f2
- Tareas sin plazo resaltadas en amarillo claro (#fff3cd)
- Tono: ejecutivo, directo, sin adornos
- NO incluyas "Estimado/a" — empieza directo con "Acta Ejecutiva"

REGLAS:
- Si hay tareas sin responsable, agregar nota: "⚠️ Tareas sin responsable asignado requieren follow-up"
- Si hay más de 5 tareas, agregar nota: "📋 Considerar priorización en próxima reunión"
- Máximo 500 palabras
```

**Mensajes de prueba:**

1. *Contexto: "Reunión semanal equipo marketing" / Notas: "- mkt: aprobar presup Q2, maría lo revisa - redes: tiktok sí, threads no por ahora - blog: necesitamos 3 posts más, juan se encarga, para el viernes - pendiente: definir KPIs nuevos - ojo: el cliente pidió cambiar la campaña, no decidimos nada"*
2. *Contexto: "Kick-off proyecto nuevo" / Notas: "nombre del proy: Atlas, arrancar en marzo, pedro lidera back, ana el front, diseño pendiente ver con outsource, presup aprobado 50k, falta definir sprint 1, weekly los lunes 10am"*
3. *Contexto: "1:1 con mi jefe" / Notas: "me dijo q voy bien, subir sueldo en junio si todo ok, quiere q lidere el proyecto nuevo, tengo q preparar propuesta para el viernes, hablar con rrhh sobre el tema de vacaciones"*

---

### Escenario 3: Generador de Feedback Profesional

**Contexto:** Necesitas dar feedback a alguien pero lo tienes en formato "emocional" o "crudo". El agente separa hechos de juicios, reformula profesionalmente usando el framework SBI (Situación-Comportamiento-Impacto), y te envía una guía de cómo entregarlo.

**Form:** textarea (feedback crudo) + select (relación: Jefe / Par / Reporte directo) + email

**SystemPrompt OR#1 — Analizar:**

```
Eres un coach de comunicación profesional especializado en feedback.

INSTRUCCIONES:
1. Lee el feedback crudo del usuario (puede ser emocional, con juicios, desorganizado)
2. Identifica la relación (jefe/par/reporte directo)
3. Separa hechos observables de juicios/opiniones
4. Identifica comportamientos específicos mencionados
5. Detecta el sentimiento predominante
6. Propón reformulaciones usando framework SBI (Situación-Comportamiento-Impacto)

FORMATO DE SALIDA (JSON estricto):
{
  "relacion": "string",
  "sentimiento": "frustración | reconocimiento | preocupación | molestia | admiración",
  "hechos": ["string (comportamientos observables)"],
  "juicios": ["string (opiniones/interpretaciones del usuario)"],
  "reformulaciones_sbi": [
    {
      "situacion": "string",
      "comportamiento": "string",
      "impacto": "string"
    }
  ],
  "tipo_feedback": "correctivo | positivo | mixto",
  "num_juicios": number,
  "riesgo_conflicto": "bajo | medio | alto"
}

REGLAS:
- "Siempre llega tarde" es un JUICIO. "Llegó 15 min tarde a las últimas 3 reuniones" es un HECHO.
- Si el usuario no da hechos específicos, en gaps indica qué datos necesita conseguir
- El riesgo de conflicto sube si: hay muchos juicios, el sentimiento es fuerte, o la relación es con un jefe
- Responde SOLO con el JSON, sin texto adicional
```

**SystemPrompt OR#2 — Generar:**

```
Eres un coach de comunicación que prepara guías de feedback profesional por email.

INSTRUCCIONES:
Recibirás un JSON con el análisis de feedback. Genera un email HTML con una "Guía de Feedback" que incluya:

1. Header: "Tu Guía de Feedback" + tipo (correctivo/positivo/mixto) + nivel de riesgo
2. Sección "Antes → Después" — tabla con 2 columnas:
   - "Lo que sentiste" (juicios originales)
   - "Cómo decirlo" (reformulación SBI)
3. Sección "Script sugerido" — texto que el usuario puede usar como base para la conversación
4. Sección "Tips de entrega" — 3 consejos según la relación y el riesgo
5. Sección "Errores a evitar" — 2 cosas que NO hacer en esta conversación
6. Nota final empática

FORMATO:
- Email HTML con estilos inline
- Tabla "Antes → Después" con columna izquierda en rojo suave (#fce4e4) y derecha en verde suave (#e4fce4)
- Tips con íconos: 💡 para tips, ⛔ para errores
- Tono: empático, profesional, como un coach que te prepara
- NO incluyas "Estimado/a" — usa "Hola,"

REGLAS:
- Si riesgo es alto: enfatizar "pedir permiso antes de dar feedback" y "elegir momento privado"
- Si es feedback a un jefe: incluir tip sobre "feedback ascendente" y cómo enmarcarlo
- Si es feedback positivo: el script debe ser breve y directo (no sobreexplicar lo bueno)
- Máximo 450 palabras
```

**Mensajes de prueba:**

1. *Relación: Par / "estoy harto de que juan nunca termina sus tareas a tiempo y yo tengo que cubrir su trabajo, la semana pasada tuve que quedarme hasta las 9pm terminando su parte del reporte y ni siquiera se disculpó"*
2. *Relación: Reporte directo / "maría es increíble, siempre entrega antes de tiempo y la calidad es excelente, quiero que sepa que la valoro pero no sé cómo decirlo sin que suene raro"*
3. *Relación: Jefe / "mi jefe nunca me da feedback, no sé si voy bien o mal, en la última evaluación solo dijo 'todo bien' y ya, necesito que me diga qué mejorar"*

---

### Plantilla para caso propio (Opción 4)

#### 3 preguntas guía

1. **¿Qué input recibes?** Describe qué tipo de texto/datos desordenados recibes regularmente en tu trabajo.
   - Tu respuesta: _______________

2. **¿Qué output necesitas?** Describe el documento/email profesional que te gustaría recibir automáticamente.
   - Tu respuesta: _______________

3. **¿Qué transforma la IA?** ¿Qué análisis debe hacer la primera IA (OR#1) para que la segunda (OR#2) pueda generar el output?
   - Tu respuesta: _______________

#### Checklist de viabilidad (mínimo 6 de 7)

| ✅ | Criterio |
|----|----------|
| | El input es texto que alguien escribe o pega |
| | El output es un email que tiene valor profesional |
| | La transformación requiere "inteligencia" (no es solo copiar/pegar) |
| | OR#1 puede extraer estructura del input (hay información que organizar) |
| | OR#2 puede generar contenido útil a partir de esa estructura |
| | Puedes probar con al menos 3 ejemplos reales |
| | El resultado es verificable (puedes comparar email recibido vs lo que esperabas) |

#### Diseña tus SystemPrompts con Claude (callback C03)

Usa este prompt en Claude:

```
Quiero diseñar 2 SystemPrompts encadenados para un agente.

Mi caso:
- Input: [describe qué escribe el usuario]
- Output: [describe qué email debería recibir]
- Contexto: [tu rol e industria]

Necesito:
1. SystemPrompt #1 (ANALIZAR): que tome el input crudo y produzca un JSON estructurado
2. SystemPrompt #2 (GENERAR): que tome el JSON y genere un email HTML profesional

Hazme preguntas antes de escribir los SystemPrompts.
Sigue el mismo formato y nivel de detalle que estos ejemplos:
[Pega un SystemPrompt de los escenarios predefinidos como referencia]
```
