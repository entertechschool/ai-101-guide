# Guía del Facilitador - Clase 07: Mi Agente Real

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Encadenamiento de IAs**: Usar el output de una IA como input de otra. OR#1 analiza (extrae estructura), OR#2 genera (produce contenido). Es la evolución de C05-C06 donde solo clasificaban.
- **Transferencia**: Aplicar los patrones aprendidos (form, webhook, Make, OpenRouter) a un caso nuevo — pero con arquitectura diferente (2 IAs en vez de Router).
- **Deploy público**: El estudiante publica su primer proyecto con URL funcional (Vercel). No es tarea — es portfolio real.
- **SystemPrompts como documentación**: Los SystemPrompts SON el "cerebro" del agente. Guardarlos y documentarlos es la pieza intelectual del proyecto (se publican en GitHub en C08).

---

## Analogías Útiles

**OR#1 es el analista, OR#2 es el redactor:**
Imagina una empresa donde alguien lee el email del cliente y llena un formulario estructurado (OR#1). Luego otro redacta la respuesta profesional basándose en ese formulario (OR#2). Mismo flujo, automatizado.

**v0 → Vercel = escribir → publicar:**
Creas el form (escribir) y lo publicas en internet (publicar). En C08 completan el ciclo con GitHub (archivar + documentar).

**Los 3 escenarios = menú con plato sugerido:**
Es más fácil elegir del menú que inventar un plato. Los escenarios dan opciones concretas para quienes se paralizan con "elige tu caso".

---

## Contexto Pedagógico

### ¿Por qué 2 IAs encadenadas?

C05-C06 demostraron que los estudiantes pueden conectar 1 IA con un Router para clasificar. C07 demuestra que pueden **encadenar 2 IAs** donde la primera prepara el input para la segunda. Esto es un patrón fundamental en automatización con IA: pipelines donde cada paso transforma los datos para el siguiente.

### ¿Por qué deploy público?

Tener una URL funcional que cualquiera puede usar es más poderoso que un screenshot en un Google Doc. El agente deployado ES el portfolio. GitHub y la documentación open-source se completan en C08, donde hay más tiempo para hacerlo bien.

### ¿Por qué escenarios predefinidos?

El diseño anterior pedía "elige tu caso" y el 30-40% se paralizaba. Los 3 escenarios eliminan la parálisis de página en blanco sin quitar la posibilidad de caso propio (opción 4). El escenario predefinido ya trae SystemPrompts listos — el estudiante solo personaliza.

### Riesgo principal

Estudiantes atascados en la configuración técnica de OR#1 (JSON malformado, headers incorrectos). Tener un escenario de Make pre-construido listo para compartir como backup.

### Callbacks pedagógicos

| Clase | Técnica | Cómo se aplica en C07 |
|-------|---------|----------------------|
| C02 | RICE + Few-shot | Estructura de los SystemPrompts |
| C03 | Socio pensante | Claude personaliza SystemPrompts |
| C05 | Form v0 + webhook | Mismo patrón, nuevo form |
| C06 | OpenRouter + Make | Ahora con 2 OpenRouter encadenados |

---

## Preparación ANTES de Clase

### Crítico — Sin esto la clase no funciona

1. **Tu propio agente funcionando** (escenario diferente al de los estudiantes)
   - Probado end-to-end: form → webhook → OR#1 → Sheets → OR#2 → Gmail
   - Muéstralo como demo en vivo. Debe funcionar sin fallas
   - Prepara 2 inputs de prueba para la demo

2. **3 escenarios probados** con Gemini Flash en OpenRouter
   - Verifica que los SystemPrompts del Apéndice producen JSON válido (OR#1)
   - Verifica que OR#2 genera HTML legible en Gmail
   - Ten los SystemPrompts listos para copiar/pegar si alguien necesita ayuda

3. **Escenario de backup en Make** para estudiantes atascados
   - Make con los 5 módulos pre-configurados
   - Listo para clonar y compartir

4. **Test de Gmail HTML**: envíate un email desde tu escenario y verifica que llega con formato (no como texto plano)

---

## Estructura de la Clase (~85 min instrucción / ~100 min con buffer)

### BLOQUE 1: Apertura (10 min)

#### Pregunta Detonadora (~4 min)

**Respuesta correcta: C** — Depende de CÓMO le pidas que las procese

**Script post-votación:**
```
"La IA puede procesar cualquier cosa desordenada.
Pero sin instrucciones claras, produce algo genérico.
La magia está en el SystemPrompt: qué analizar, qué generar, en qué formato.
Hoy construyen un agente con 2 cerebros: uno analiza, otro genera."
```

#### Demo: Tu Agente EN VIVO (~6 min)

Muestra tu agente completo. El impacto es ver el flujo de punta a punta:

1. Abre tu formulario (URL de Vercel) — "Este es mi form público, cualquiera puede usarlo"
2. Escribe algo desordenado en el textarea — en vivo, sin preparar
3. Click en enviar
4. Muestra en Make History cómo pasa por los 5 módulos
5. Abre tu correo → muestra el email HTML que llegó
**Script clave:**
```
"Escribí esto en 30 segundos. Me llegó un email profesional.
Mismo patrón que C05-C06. Pero ahora hay 2 IAs:
una que analiza mi caos, otra que genera el email.
Y esto va a estar público en Vercel. Esto es lo que van a construir."
```

---

### BLOQUE 2: Contexto + Arquitectura (10 min)

#### De clasificar a generar (~4 min)
- Slide "La evolución C05-C06 → C07"
- Enfatizar: antes la IA ponía una etiqueta (URGENTE), ahora CREA contenido
- "En C06 la IA decidía. En C07 la IA produce."

#### Nueva arquitectura (~3 min)
- Slide con diagrama de 5 módulos
- Explicar: "OR#1 es el analista — lee el caos y extrae estructura en JSON. OR#2 es el redactor — toma la estructura y escribe un email profesional."
- Preguntar: "¿Por qué separar en 2? ¿No puede hacer todo en 1?"
- Respuesta: "Especialización. Cada IA tiene un solo trabajo = mejor calidad."

#### Anti-Hype (~3 min)
```
"Tu agente va a generar emails mediocres al principio.
El JSON de OR#1 puede venir malformado.
Gmail puede mostrar HTML como texto plano.
Eso es normal. Lo importante es que sepan diagnosticar y mejorar."
```

---

### BLOQUE 3: Lab Parte 1 — Diseñar (10 min)

Los estudiantes eligen escenario y revisan/personalizan SystemPrompts:

- **[0-3 min]** Elegir escenario de la tabla (1, 2, 3 o propio)
- **[3-10 min]** Revisar los SystemPrompts del Apéndice + personalizar con Claude

**Intervención a los 5 min:** Si alguien no ha elegido escenario:
- "¿Tienes reuniones? Escenario 2. ¿Das feedback? Escenario 3. ¿Tienes ideas? Escenario 1."
- Si nada funciona → Escenario 2 (Notas de Reunión) es el más universal

> **Checkpoint ~min 10:** "¿Quién tiene sus 2 SystemPrompts listos?" — Manos arriba.

---

### BLOQUE 4: Lab Parte 2 — Construir (40 min)

#### Form v0 (8 min)
- Nuevo form, no reusar el de PetShop — este tiene campos diferentes
- Verificar que envía JSON al webhook

#### Make: 5 módulos (25 min)
- **Webhook** (~5 min): Crear nuevo escenario + webhook + test
- **OpenRouter #1** (~7 min): HTTP module + headers + SystemPrompt #1 + temperature 0.3
- **Google Sheets** (~5 min): Crear hoja + mapear columnas del JSON
- **OpenRouter #2** (~5 min): Mismo HTTP module + SystemPrompt #2 + temperature 0.7
- **Gmail** (~3 min): Enviar con output de OR#2 como HTML

**Errores frecuentes en este bloque:**
- OR#1 devuelve texto en vez de JSON → revisar SystemPrompt, agregar "Responde SOLO con JSON"
- OR#2 no recibe el JSON de OR#1 → verificar mapping: `{{choices[0].message.content}}`
- Gmail muestra HTML como texto → marcar opción "HTML" en el módulo Gmail
- Headers de OpenRouter incorrectos → verificar `Bearer` antes del API key

#### Conectar + smoke test (2 min)
- Webhook URL en form → deploy → enviar 1 mensaje → verificar email + Sheets

> **Checkpoint ~min 50:** "¿Quién tiene form en Vercel y email funcionando?"

---

### BLOQUE 5: Lab Parte 3 — Verificar (5 min)

#### Test final + verificar (5 min)
- 2 mensajes desde URL de Vercel → verificar emails + Sheets
- Checklist: email HTML + Sheets 2 registros + URL funcional
- Recordar: **copiar sus 2 SystemPrompts** y tenerlos accesibles (para C08)

> **Checkpoint ~min 55 del lab:** "¿Quién tiene agente funcionando + SystemPrompts guardados?"

---

### BLOQUE 6: Cierre (5 min)

#### Reflexión rápida (~2 min)
- "¿Quién recibió un email que realmente usaría en su trabajo?"
- "¿Qué escenario eligieron? ¿Alguien hizo caso propio?"

#### Preview C08 (~3 min)
```
"Próxima clase hacemos 3 cosas grandes:
1. Publican su agente en GitHub — su primer proyecto open-source
2. Crean un post de LinkedIn con imagen generada por IA
3. Pitches de 3 minutos — problema + post + demo rápida"
```

**Tarea para la próxima clase:**
1. **Crear cuenta en GitHub** si no tienes (github.com — es gratis)
2. **SystemPrompts copiados** — tener OR#1 y OR#2 accesibles
3. Verificar que la URL de Vercel funciona públicamente
4. Tener cuenta de **LinkedIn** abierta
5. Tener cuenta de **Gemini** (gemini.google.com)
6. Pulir SystemPrompts — probar con 3+ mensajes variados

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No sé qué escenario elegir" | Parálisis de elección | "¿Tienes reuniones? Escenario 2. Es el más universal" |
| "OR#1 devuelve texto, no JSON" | SystemPrompt no es claro | Agregar al prompt: "Responde SOLO con el JSON, sin texto adicional ni markdown" |
| "OR#2 no recibe nada" | Mapping incorrecto | Verificar que OR#2 lee `{{choices[0].message.content}}` del módulo OR#1 |
| "El email llega como texto plano" | Gmail no está en modo HTML | En el módulo Gmail → marcar opción "HTML" en el campo de contenido |
| "El JSON viene con backticks" | OR#1 envuelve en markdown | Agregar al SystemPrompt: "No uses markdown. Solo JSON puro" |
| "El email es genérico/malo" | SystemPrompt de OR#2 poco específico | Iterar el prompt: más instrucciones de formato, tono, secciones |

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~4 | PD votada | Discusión sobre análisis vs clasificación completada |
| ~10 | Demo completada | Estudiantes vieron el flujo completo |
| ~20 | SystemPrompts listos (Lab P1) | "¿Quién tiene 2 SystemPrompts?" |
| ~35 | Make con OR#1 funcionando | "¿Quién tiene JSON válido saliendo de OR#1?" |
| ~50 | Agente completo en Vercel | "¿Quién tiene email + Sheets funcionando?" |
| ~55 | Test final + SystemPrompts guardados | "¿Quién tiene 2 mensajes probados + SystemPrompts copiados?" |

---

## Tips de Facilitación

### Si el grupo avanza rápido:
- Que prueben con inputs extremos: texto muy corto, muy largo, en otro idioma
- Que comparen outputs entre escenarios diferentes
- Que ayuden a compañeros atascados con la configuración de Make

### Si OR#1 produce JSON inválido consistentemente:
- Agregar al SystemPrompt: "IMPORTANTE: No incluyas ```json ni backticks. Solo el JSON puro."
- Reducir temperature a 0.1 temporalmente
- Probar con un input más simple primero

### Manejo de tiempo:
- **Parte 1** (diseñar, 10 min): Rápido si eligen escenario predefinido. Si a los 5 min no eligieron, intervén.
- **Parte 2** (construir, 40 min): Donde más se atoran es en OR#1 (JSON). Tener backup de Make listo.
- **Parte 3** (verificar, 5 min): Lo más sencillo. Asegurar que copien SystemPrompts para C08.
- **Buffer real:** Los ~10 min liberados de Parte 3 son buffer extra para Parte 2 (Make).

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

```
"Próxima clase hacemos 3 cosas grandes:
1. Publican su agente en GitHub — su primer proyecto open-source
2. Crean un post de LinkedIn con imagen generada por IA
3. Pitches de 3 minutos — problema + post + demo rápida"
```

**Tarea para la próxima clase:**
1. **Crear cuenta en GitHub** si no tienes (github.com — es gratis)
2. **SystemPrompts copiados** — tener OR#1 y OR#2 accesibles
3. Verificar que URL de Vercel funciona públicamente
4. Tener cuenta de **LinkedIn** abierta
5. Tener cuenta de **Gemini** (gemini.google.com)
6. Pulir SystemPrompts — probar con 3+ mensajes variados
