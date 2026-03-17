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

**Post-votación:** "La IA procesa cualquier cosa desordenada. Pero sin instrucciones claras, produce algo genérico. Hoy construyen un agente con 2 cerebros: uno analiza, otro genera."

#### Demo: Tu Agente EN VIVO (~6 min)

Flujo: Abre tu form (URL Vercel) → escribe algo desordenado en vivo → envía → muestra Make History (5 módulos) → abre tu correo con el email HTML.

**Mensaje clave:** "Escribí esto en 30 segundos. Me llegó un email profesional. 2 IAs: una analiza mi caos, otra genera el email. Esto es lo que van a construir."

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

**Mensaje clave:** "Tu agente va a generar emails mediocres al principio. JSON malformado, HTML como texto plano — es normal. Lo importante es saber diagnosticar y mejorar."

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

"Próxima clase: GitHub (open-source) + LinkedIn (post con imagen IA) + Pitches (3 min c/u)."

**Tarea:** Cuenta GitHub + SystemPrompts copiados + URL Vercel funcional + cuenta LinkedIn + cuenta Gemini + pulir prompts (3+ mensajes).

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

## ✅ Señales de Comprensión

**ENTIENDE cuando:**
- Explica por qué separar en 2 IAs mejora la calidad (especialización)
- Puede diagnosticar si un problema está en OR#1 (JSON malo) o en OR#2 (email genérico)
- Entiende que los SystemPrompts son la pieza intelectual del proyecto

**NECESITA AYUDA cuando:**
- No distingue qué hace OR#1 vs OR#2
- Copia SystemPrompts sin entender qué modificar para su caso
- Se atasca en la configuración técnica de Make sin pedir ayuda

---

## 🔀 Diferenciación

**Estudiantes avanzados:** Que prueben con inputs extremos (muy corto, otro idioma), que agreguen un campo extra al form, que comparen outputs entre escenarios.

**Estudiantes con dificultades:** Que usen escenario predefinido sin modificar, que copien SystemPrompts del Apéndice tal cual, checkpoint intermedio a los 20 min.

---

## 🎭 Dinámicas de Clase

### "Antes y después"
```
Facilitador: [Lee input desordenado en voz alta]
"¿Qué harían con esto si les llega por email? ¿Cuánto tardarían?"
[Después de la demo] "El agente lo hizo en segundos. Ese es el delta."
```

---

## 💡 Ejemplos Listos para Usar

### SystemPrompt OR#1 genérico (para caso propio):
```
Analiza el siguiente input del usuario. Extrae:
1. Tema principal
2. Puntos clave (máximo 5)
3. Tono detectado
4. Acción sugerida

Responde SOLO con JSON, sin markdown ni backticks.
```

---

## ❓ Preguntas Frecuentes

### "¿Por qué no usar Claude en vez de Grok?"
Claude es más potente pero requiere API de pago. Grok Free permite experimentar sin costo. Las técnicas funcionan igual.

### "¿Puedo usar mi agente de C06 como base?"
No recomendado. C07 usa arquitectura diferente (2 IAs encadenadas vs Router). Mejor crear escenario nuevo.

---

## 🪞 Reflexión Post-Clase

1. **¿La demo convenció?** — Si no hubo reacciones, puede que el input fue poco impactante.
2. **¿Los escenarios predefinidos eliminaron la parálisis?** — Si más del 30% eligió caso propio, bien.
3. **¿OR#1 produjo JSON válido?** — Si muchos tuvieron problemas, ajustar el SystemPrompt de ejemplo.
4. **¿Todos tienen SystemPrompts guardados para C08?** — Crítico para la próxima clase.

---

## Tips de Facilitación

- **Grupo rápido:** Que prueben inputs extremos, comparen escenarios, ayuden a compañeros
- **JSON inválido:** Agregar "No uses markdown ni backticks. Solo JSON puro." + reducir temperature a 0.1
- **Tiempo:** P1 diseñar (10 min) rápido con escenarios. P2 construir (40 min) es donde se atoran (OR#1). P3 verificar (5 min) + copiar SystemPrompts para C08

---

## Conexión con la Próxima Clase

"Próxima clase: GitHub (open-source) + LinkedIn (post con imagen IA) + Pitches (3 min c/u)."

**Tarea:** Cuenta GitHub + SystemPrompts copiados + URL Vercel funcional + cuenta LinkedIn + cuenta Gemini.
