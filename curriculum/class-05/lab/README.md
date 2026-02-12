# Lab 05: Mi Agente de Triage

En Clase 02 clasificaste mensajes manualmente. Hoy construyes el **cerebro** de un agente: un formulario con v0 que envía datos a Make, donde la IA clasifica con OpenRouter. El agente piensa — en C06 le daremos manos.

> ⏱️ **Tiempo:** 90 minutos

### 🎯 Objetivo

Crear la primera mitad de un agente: formulario v0 con bloque debug → Webhook Make → OpenRouter (clasificación IA).

## Arquitectura

```
[Formulario v0 + Debug] → [Webhook Make] → [OpenRouter/Grok]
```

| Componente | Qué hace | Herramienta |
|------------|----------|-------------|
| **Formulario** | Captura el mensaje del cliente | v0 (form + bloque debug) |
| **Webhook** | Recibe datos y activa el flujo | Make |
| **Decisión** | Clasifica con IA (SystemPrompt + UserPrompt) | Grok Free vía OpenRouter |

> 💡 En C06 agregaremos Gmail, Router y Google Sheets para completar el agente.

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Cuenta de Make | Dashboard accesible |
| API Key de OpenRouter | Generada y copiada |
| Prompt de triage de C02 | En tu Google Doc |
| Wireframe o ejemplo de form | Screenshot o imagen lista |
| Google Doc nuevo | Para documentar tu agente |

---

## Parte 1: Concepto (15 min)

**Pregunta detonadora 1:** ¿Cuál es la diferencia entre una automatización y un agente IA?

**Pregunta detonadora 2:** Imagina que recibes 100 mensajes al día. Con tu prompt manual de C02, ¿cuánto te toma clasificarlos?

El facilitador envía 3 mensajes desde un formulario. Observa cómo cada uno recibe una clasificación diferente en Make History.

```
Automatización: IF mensaje → THEN reenviar a soporte (siempre igual)
Agente:         IF mensaje → IA LEE → DECIDE categoría → acción diferente
```

✅ **Checkpoint:** Entiendes la diferencia entre automatización y agente.

---

## Parte 2: Crear tu Formulario con v0 (30 min)

### 2.1 Scaffolding con Gemini (refuerzo C03)

No sabes qué pedirle a v0? Usa Gemini como socio pensante — pídele que te ayude a estructurar el prompt antes de ir a v0:

```
Necesito crear un formulario de contacto para [mi negocio].
Ayúdame a definir: qué campos necesito, qué estilo visual
es apropiado, y cómo debería verse el layout.
Dame 3 opciones con justificación para cada una.
```

Elige la opción que mejor represente tu marca.

### 2.2 Prompt + wireframe a v0 (refuerzo Few-shot C02)

Abre [v0.dev](https://v0.dev) y escribe un prompt. Adjunta tu wireframe como ejemplo visual:

```
Crea un formulario de contacto para PetShop Express con:
- Campo: Nombre del cliente
- Campo: Email
- Campo: Mensaje (textarea)
- Botón de enviar
- Diseño limpio y profesional
[Adjunta tu wireframe como ejemplo de estilo]
```

### 2.3 Bloque debug

Pide a v0 que agregue un panel de debug al formulario:

```
Agrega un bloque de debug debajo del formulario que:
- Muestre la respuesta del servidor después de enviar
- Muestre un indicador de estado (enviando/éxito/error)
- Incluya un botón de "Reintentar" si falla la conexión
- Solo sea visible después del primer envío
```

> 💡 El bloque debug te permite ver si tu form se conectó bien al webhook sin abrir Make.

### 2.4 Deploy + copiar URL

1. Haz clic en **Deploy** para publicarlo
2. Copia la URL de tu formulario
3. Guárdala — la conectarás al webhook de Make

> 💡 Si v0 no funciona, el facilitador compartirá un formulario pre-armado.

✅ **Checkpoint:** Formulario deployado con URL pública y bloque debug visible.

---

## Parte 3: Construir el Agente en Make (35 min)

### 3.1 Clona el template

El facilitador comparte el link del template. Clónalo a tu cuenta. Tiene 2 módulos: `[Webhook] → [OpenRouter]`

### 3.2 Configura el Webhook

Copia la URL del webhook. Tu formulario v0 enviará datos a esta URL.

### 3.3 Configura OpenRouter — API Key

Este paso es nuevo y crítico. En el módulo OpenRouter de Make:

1. Haz clic en el módulo OpenRouter → **Create a connection**
2. Nombre de la conexión: "Mi OpenRouter"
3. Pega tu API Key de OpenRouter (la que generaste antes de clase)
4. Selecciona el modelo: **grok-3-mini-beta:free**
5. Haz clic en **Save** → espera el checkmark verde ✅
6. Si ves error, verifica que la key no tenga espacios al inicio o final

> 💡 El nombre exacto del modelo puede cambiar — verifica en [openrouter.ai/models](https://openrouter.ai/models) si no lo encuentras.

> ⚠️ Si tu key no funciona, pide la key de backup al facilitador.

### 3.4 Personaliza el SystemPrompt

En el módulo OpenRouter, edita el **SystemPrompt** — el ROL y REGLAS de tu agente:

```
Eres un agente de triage automático para PetShop Express.
Clasifica cada mensaje en UNA categoría.

CATEGORÍAS:
- URGENTE: Salud animal, deadline real, impacto financiero
- CONSULTA: Preguntas sobre productos, disponibilidad
- VENTA: Interés en compra, cotizaciones, pedidos corporativos

REGLAS:
- Tono agresivo NO es urgencia. Urgencia = impacto real
- "No urgente" + deadline esta semana → URGENTE
- Ambigüedad → CONSULTA

Formato de respuesta:
CATEGORÍA: [URGENTE|CONSULTA|VENTA]
RESUMEN: [1 línea]
ACCIÓN: [qué hacer]
```

### 3.5 Personaliza el UserPrompt

El UserPrompt mapea los datos del formulario:

```
Nuevo mensaje de: {{nombre}}
Email: {{email}}
Mensaje: {{mensaje}}
```

Verifica que los campos coincidan con tu formulario v0.

### 3.6 Conecta tu form al webhook

Actualiza tu formulario v0 para que envíe datos a la URL del webhook de Make. Usa el bloque debug para verificar que la conexión funciona.

✅ **Checkpoint:** Template clonado, API key conectada (checkmark verde), SystemPrompt personalizado, form conectado.

---

## Parte 4: Primer Test — Ver al Agente Pensar (10 min)

1. Activa tu escenario en Make (switch **ON**)
2. Envía 1 mensaje desde TU formulario
3. Ve a **Make History** → revisa el output de OpenRouter
4. ¿La clasificación fue correcta? ¿El formato es el que pediste?
5. Envía 1-2 mensajes más con categorías diferentes
6. Toma screenshot de Make execution mostrando la clasificación

> 💡 Usa el bloque debug de tu form para ver si el envío fue exitoso antes de revisar Make.

✅ **Checkpoint:** Al menos 2 mensajes clasificados visibles en Make History.

---

## 📝 Entregable (Parcial — se completa en C06)

**Google Doc con 3 secciones:**

1. **Mi Formulario** — URL del form v0 deployado + screenshot (con bloque debug visible)
2. **Mi Agente (cerebro)** — Screenshot del flujo en Make (2 módulos) + SystemPrompt completo
3. **Primer Test** — Screenshot de Make History mostrando clasificación de al menos 2 mensajes

**Entrega:** Link público del Google Doc.

📌 **Próxima clase** completamos el agente: Gmail + Router + Google Sheets + battle de agentes.
