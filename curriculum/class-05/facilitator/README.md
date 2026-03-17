# Guía del Facilitador - Clase 05: Tu Primer Agente IA

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Agente IA**: Automatización que usa IA para DECIDIR, no solo ejecutar reglas fijas.
- **Form → Webhook → OpenRouter**: La arquitectura del cerebro del agente (hoy).
- **SystemPrompt**: Define el ROL y REGLAS del agente (lo que "es"). Permanente.
- **UserPrompt**: Mapea los datos de cada mensaje (lo que "recibe"). Cambia por mensaje.
- **Bloque debug**: Panel en v0 que muestra respuesta del servidor + botón reintentar.
- **Scaffolding con Gemini**: Usar Gemini para estructurar el prompt antes de ir a v0.
- **Supervisión**: Un agente no reemplaza al humano — prioriza su trabajo.

---

## Analogías Útiles

**Agente como recepcionista inteligente:**
Un recepcionista no reenvía todos los mensajes al mismo lugar. Lee, decide quién debe atenderlo, y lo direcciona. Hoy construimos al recepcionista que LEE — en C06 le damos las puertas a donde enviar.

**Automatización vs agente:**
Automatización = contestador automático ("Presione 1 para soporte, 2 para ventas"). Agente = recepcionista que LEE tu mensaje y decide a quién derivarte.

**SystemPrompt como manual del empleado:**
Si contratas a alguien y no le das instrucciones claras, tomará malas decisiones. El SystemPrompt ES el manual de tu agente.

**Errores del agente como errores de un junior:**
Un empleado nuevo se equivoca. No lo despides — le das mejor contexto. Con el agente igual: errores = oportunidad de mejorar el SystemPrompt.

---

## Contexto Actual

### Por qué triage como caso base

La conexión C02 → C05 es intencional y potente:
- En C02, los estudiantes ya clasificaron estos mismos mensajes manualmente
- Entienden los criterios, los errores esperados y las limitaciones
- Ver su trabajo manual convertido en agente automático es un "momento wow" genuino

### Por qué esta arquitectura

| Decisión | Razón |
|----------|-------|
| Form en v0 (no curl/JSON manual) | Origen de datos tangible, refuerza M1 |
| Make (no Zapier) | Más visual, plan free generoso, módulo OpenRouter nativo |
| OpenRouter nativo (no HTTP genérico) | SystemPrompt + UserPrompt separados, sin JSON manual |
| Gemini como scaffolding | Ya la conocen de C04, refuerza socio pensante de C03 |
| Template pre-armado (2 módulos) | Reduce fricción técnica, foco en personalización |
| Sin Gmail en C05 | Menos complejidad, foco en el cerebro. Gmail se agrega en C06 |

### Descubrimientos de clase real

1. **v0 + debug fue WOW**: Gemini como scaffolding + bloque debug en v0 = gran descubrimiento
2. **Tiempo justo**: Solo alcanza para Webhook + OpenRouter. Gmail se mueve a C06
3. **API Key necesita paso explícito**: Ver sección dedicada más abajo

---

## Preparación ANTES de Clase (Crítico)

### Lo que DEBES tener listo:

1. **Formulario de backup en v0**
   - Crea y despliega un formulario de PetShop Express funcional con bloque debug
   - Tenlo listo como plan B si algún estudiante no puede crear el suyo

2. **Template de Make funcionando**
   - Crea el escenario con 2 módulos: Webhook → OpenRouter
   - Configura OpenRouter con SystemPrompt + UserPrompt separados
   - Pruébalo enviando datos desde el form → ver clasificación en History
   - Genera el link de clonación para estudiantes

3. **Wireframe base**
   - Prepara un wireframe simple de formulario de contacto
   - Los estudiantes lo usarán como ejemplo para v0 (Few-shot)

4. **API Key de OpenRouter de respaldo**
   - Ten una key propia como backup
   - Grok Free tiene límites — verifica que funcione antes de clase

5. **Demo ejecutada y verificada**
   - Corre la demo completa: enviar desde form → ver clasificación en Make History
   - Guarda screenshots de backup de cada paso

---

## Cómo Configurar OpenRouter API Key en Make

Este paso causó confusión en clase. Guía paso a paso:

### Pasos:
1. En Make, haz clic en el módulo OpenRouter
2. Haz clic en **Create a connection**
3. Nombre: "Mi OpenRouter" (o el nombre que quieran)
4. Pega la API Key de OpenRouter
5. Selecciona modelo: **grok-3-mini-beta:free**
6. Clic en **Save** → espera checkmark verde ✅

### Troubleshooting:

| Error | Causa probable | Solución |
|-------|---------------|----------|
| "Connection failed" | Key con espacios al inicio/final | Copiar key de nuevo, sin espacios |
| "Model not found" | Nombre del modelo incorrecto | Seleccionar exacto: grok-3-mini-beta:free |
| "Rate limit exceeded" | Key agotada o muchos intentos | Usar key de backup del facilitador |
| "Invalid API key" | Key expirada o mal copiada | Generar nueva key en openrouter.ai |
| Checkmark no aparece | Conexión lenta | Esperar 10 seg, si no → reintentar |

> 💡 El nombre exacto del modelo puede cambiar — verifica en [openrouter.ai/models](https://openrouter.ai/models){:target="_blank"} antes de clase.

> ⚠️ Ten tu key de backup lista. Si más de 2 estudiantes tienen problemas, compártela.

---

## Guía para el Bloque Debug en v0

### Qué pedir a v0:

Después de generar el formulario base, agregar un prompt adicional:

```
Agrega un bloque de debug debajo del formulario que:
- Muestre la respuesta del servidor después de enviar
- Muestre un indicador de estado (enviando/éxito/error)
- Incluya un botón de "Reintentar" si falla la conexión
- Solo sea visible después del primer envío
```

### Cómo funciona:
- Al enviar: panel con HTTP status (200 = verde, error = rojo + reintentar)
- Ahorra tiempo: el estudiante no necesita abrir Make para saber si el envío funcionó
- Si v0 no genera buen debug → compartir formulario de backup que ya lo incluya

---

## Momentos Clave de la Clase

### Pregunta Detonadora (~5 min)

**Respuesta correcta:** B — Un agente usa IA para tomar decisiones

**Post-votación:** Enfatizar la diferencia clave: automatización = reglas fijas (IF/THEN), agente = IA DECIDE. "Si una IA LEE el email y DECIDE a dónde va, eso es un agente."

---

### Demo Principal: Agente en Vivo (~10 min)

**Preparación:** Formulario v0 abierto + escenario de Make activo.

**Flujo:** Enviar 3 mensajes desde el form. Mostrar debug (éxito) + Make History (clasificación). Preguntar antes de revelar el tercero: "¿Qué creen que hizo con este?". Callback a C02: "El tono agresivo no siempre es urgencia real."

**Si algo sale mal:** Grok tarda → "modelos free son lentos". Clasifica mal → "¿Qué cambiarían en el SystemPrompt?". Make falla → screenshots de backup.

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No puedo crear la API key" | Confusión con OpenRouter | Ver sección "Cómo Configurar OpenRouter API Key" |
| "v0 no genera lo que quiero" | Prompt sin wireframe | "Adjunta tu wireframe — Few-shot visual" |
| "v0 no me deja hacer deploy" | Cuenta limitada o error | Compartir formulario de backup |
| "No sé qué pedir para el debug" | No entiende el concepto | Compartir el prompt exacto de la guía |
| "Make no me deja clonar" | Problema de cuenta | Verificar cuenta free activa |
| "El agente no responde" | Webhook no activo o form no conectado | Verificar escenario ON + URL correcta |
| "Siempre clasifica todo igual" | SystemPrompt genérico | "¿Tiene categorías específicas?" |
| "Esto es muy técnico para mí" | Intimidación ante APIs | "Lo técnico está en el template. Tu trabajo es el PROMPT" |

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~5 | Pregunta detonadora 1 | Manos levantadas, participación |
| ~8 | Pregunta detonadora 2 | Discusión sobre escala + supervisión |
| ~18 | Demo completa | "¿Vieron la clasificación en Make History?" |
| ~48 | Formulario v0 + debug deployado | "¿Quién tiene su form con debug funcionando?" |
| ~58 | Template clonado | "¿Quién tiene los 2 módulos en Make?" |
| ~68 | API Key conectada | "¿Quién tiene el checkmark verde?" ⚠️ |
| ~83 | SystemPrompt + UserPrompt | "¿Quién ya personalizó ambos prompts?" |
| ~88 | Form conectado al webhook | "¿Quién tiene todo conectado?" |
| ~95 | Primer test exitoso | "¿Quién ve clasificación en Make History?" |

> ⚠️ El checkpoint de API Key (~min 68) es el más crítico. Si alguien no lo pasa, usa la key de backup inmediatamente. No pierdas tiempo troubleshooting individual.

---

## Sección Anti-Hype: Cómo Manejarla

**Mensaje clave:** "Su agente se va a equivocar. Garantizado. En C02 la IA confundía tono con urgencia. Su agente hará lo mismo — a menos que mejoren el SystemPrompt. La diferencia: con un agente, el error se repite automáticamente."

---

## ✅ Señales de Comprensión

**ENTIENDE cuando:**
- Explica la diferencia entre automatización (IF/THEN fijo) y agente (IA decide) con sus palabras
- Identifica que el SystemPrompt es lo que define la calidad de la decisión del agente
- Puede diagnosticar por qué una clasificación salió mal ("le falta contexto al prompt")

**NECESITA AYUDA cuando:**
- Copia el SystemPrompt sin modificar las categorías para su contexto
- No puede explicar qué hace el UserPrompt vs el SystemPrompt
- Asume que el agente "piensa" — no entiende que solo sigue reglas del prompt

---

## 🔀 Diferenciación

**Estudiantes avanzados:** Que personalicen categorías a su trabajo real, que agreguen una categoría extra (ej: SPAM), que experimenten con diferentes temperaturas en OpenRouter.

**Estudiantes con dificultades:** Que usen el template tal cual sin personalizar, emparejar con alguien avanzado, checkpoint intermedio extra a los 30 min del lab.

---

## 🎭 Dinámicas de Clase

### "Automatización o Agente"
```
Facilitador: "Voy a describir procesos. Levanten la mano si es AUTOMATIZACIÓN o AGENTE."
- "Un email llega y se reenvía a soporte" → Automatización
- "Un email llega, se lee y se decide a quién enviar" → Agente
- "Cada lunes se genera un reporte" → Automatización
- "Se analiza un texto y se decide qué hacer" → Agente
```

### "Predice la clasificación"
```
Facilitador: [Lee un mensaje de cliente en voz alta]
"¿Cómo clasificaría el agente esto? ¿URGENTE, CONSULTA o VENTA?"
[Tomar 2-3 predicciones antes de enviar al agente]
"Veamos si el agente coincide con ustedes..."
```

---

## 💡 Ejemplos Listos para Usar

### SystemPrompt adaptado por industria:
| Industria | Categorías | Regla clave |
|-----------|-----------|-------------|
| E-commerce | URGENTE, CONSULTA, VENTA, DEVOLUCIÓN | Deadline < 48h → URGENTE |
| Servicios | URGENTE, COTIZACIÓN, SOPORTE, FEEDBACK | Impacto económico → URGENTE |
| Educación | URGENTE, ACADÉMICO, ADMINISTRATIVO, TÉCNICO | Plazo de entrega → URGENTE |

---

## ❓ Preguntas Frecuentes

### "¿Puedo usar otro modelo que no sea Grok?"
Sí. OpenRouter tiene muchos modelos. Grok Free es para practicar sin costo. Las técnicas de SystemPrompt funcionan igual en cualquier modelo.

### "¿Esto funciona con más de 100 mensajes?"
Sí, pero el plan free de Make tiene límite de 1,000 operaciones/mes. Para producción real necesitarías un plan de pago.

### "¿Qué pasa si mi agente clasifica mal?"
Mejoras el SystemPrompt. Agrega reglas más específicas, ejemplos de clasificación, o condiciones edge-case. Es iterativo.

---

## 🪞 Reflexión Post-Clase

1. **¿El concepto agente vs automatización quedó claro?** — Si más de 2 confunden, reforzar en C06.
2. **¿La configuración de API Key fue fluida?** — Ajustar protocolo si hubo fricción.
3. **¿Quiénes se intimidaron con lo técnico?** — Identificar para seguimiento en C06.
4. **¿El bloque debug en v0 funcionó como se esperaba?** — Documentar si hay que ajustar el prompt.

---

## Tips de Facilitación

- **Fricción técnica:** Prioriza backup (form + template + API key). Si v0 falla, comparte tu form pre-armado
- **Grupo rápido:** Que personalicen categorías a su trabajo real
- **Intimidados:** "Lo técnico ya está en el template. Tu trabajo es el PROMPT." Emparejar con alguien que va bien

---

## Conexión con la Próxima Clase

> "Hoy construimos el cerebro — recibe, piensa y clasifica.
> Próxima clase: manos (Gmail), inteligencia (Router), memoria (Sheets).
> Y battle: ¿quién tiene el mejor agente?"

**Tarea:** Google Doc con URL form v0 (debug), screenshot Make (2 módulos), SystemPrompt, screenshot Make History.
