# Lab 05: Mi Agente de Triage

En Clase 02 clasificaste mensajes manualmente. Hoy ese proceso corre solo. Crearás un formulario con v0, conectarás un agente en Make que clasifica con IA y envía la decisión por email.

> ⏱️ **Tiempo:** 60 minutos

### 🎯 Objetivo

Crear un agente que recibe mensajes desde un formulario, los clasifica con IA (Grok vía OpenRouter) y envía un email con la clasificación.

## Arquitectura

```
[Formulario v0] → [Webhook Make] → [OpenRouter/Grok] → [Gmail]
```

| Componente | Qué hace | Herramienta |
|------------|----------|-------------|
| **Formulario** | Captura el mensaje del cliente | v0 (form deployado) |
| **Webhook** | Recibe datos y activa el flujo | Make |
| **Decisión** | Clasifica con IA (SystemPrompt + UserPrompt) | Grok Free vía OpenRouter |
| **Acción** | Envía email con categoría y acción sugerida | Gmail en Make |

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

**Pregunta detonadora:** ¿Cuál es la diferencia entre una automatización y un agente IA?

El facilitador envía 3 mensajes desde un formulario. Observa cómo cada uno recibe una clasificación diferente y un email distinto.

```
Automatización: IF mensaje → THEN reenviar a soporte (siempre igual)
Agente:         IF mensaje → IA LEE → DECIDE categoría → EMAIL diferente
```

✅ **Checkpoint:** Entiendes la diferencia entre automatización y agente.

---

## Parte 2: Crear tu Formulario con v0 (30 min)

### 2.1 Genera tu form con Few-shot (refuerzo C02)

Abre [v0.dev](https://v0.dev) y escribe un prompt. Adjunta tu wireframe como ejemplo visual — igual que Few-shot en C02:

```
Crea un formulario de contacto para PetShop Express con:
- Campo: Nombre del cliente
- Campo: Email
- Campo: Mensaje (textarea)
- Botón de enviar
- Diseño limpio y profesional
[Adjunta tu wireframe como ejemplo de estilo]
```

### 2.2 Usa Gemini como clarificador (refuerzo C03)

Si no estás seguro del estilo, abre Gemini y pide 3 opciones con justificación. Elige la que mejor represente tu marca y ajusta el prompt de v0.

### 2.3 Despliega tu formulario

1. Haz clic en **Deploy** para publicarlo
2. Copia la URL de tu formulario
3. Guárdala — la conectarás al webhook de Make

> 💡 Si v0 no funciona, el facilitador compartirá un formulario pre-armado.

✅ **Checkpoint:** Formulario deployado con URL pública.

---

## Parte 3: Construir el Agente en Make (35 min)

### 3.1 Clona el template

El facilitador comparte el link del template. Clónalo a tu cuenta. Tiene 3 módulos: `[Webhook] → [OpenRouter] → [Gmail]`

### 3.2 Configura el Webhook

Copia la URL del webhook. Tu formulario v0 enviará datos a esta URL.

### 3.3 Personaliza el SystemPrompt

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

### 3.4 Personaliza el UserPrompt

El UserPrompt mapea los datos del formulario:

```
Nuevo mensaje de: {{nombre}}
Email: {{email}}
Mensaje: {{mensaje}}
```

Verifica que los campos coincidan con tu formulario v0.

### 3.5 Configura Gmail

- **Para:** Tu email personal
- **Asunto:** `[{{CATEGORÍA}}] Nuevo mensaje de {{nombre}}`
- **Cuerpo:** Categoría + resumen + acción sugerida

### 3.6 Conecta tu form al webhook

Actualiza tu formulario v0 para que envíe datos a la URL del webhook de Make.

✅ **Checkpoint:** Agente armado, Gmail configurado, form conectado.

---

## Parte 4: Probar con 5 Mensajes (15 min)

Activa tu escenario en Make (switch ON). Desde TU formulario, envía los 5 mensajes de PetShop Express de C02:

1. Perro con dieta especial, pedido retrasado
2. Consulta sobre rascador para gatos
3. Cliente enojado quiere reembolso
4. Factura pendiente, "no es urgente" pero vence el viernes
5. Vitaminas que no funcionaron

Revisa tu Gmail y documenta en tu Google Doc:

| # | Mensaje (resumen) | Categoría | ¿Correcto? | Acción sugerida |
|---|-------------------|-----------|------------|-----------------|
| 1 | Perro dieta especial | | | |
| 2 | Rascador para gatos | | | |
| 3 | Cliente enojado reembolso | | | |
| 4 | Factura "no urgente" | | | |
| 5 | Vitaminas no funcionaron | | | |

✅ **Checkpoint:** 5 mensajes enviados, 5 emails recibidos con clasificación.

---

## Parte 5: Análisis Crítico (10 min)

Abre tu Google Doc de C02 y compara: ¿el agente clasificó igual que tú manualmente? ¿Cometió los mismos errores?

**Documenta 1 falla:**

```
FALLA DEL AGENTE:
- Mensaje #: ___
- Qué hizo: ___
- Qué debería haber hecho: ___
- Causa probable: ___
- Cómo mejoraría el SystemPrompt: ___
```

**Reflexión:** ¿Qué proceso de TU trabajo podría ser un agente como este?

## 📝 Entregable

**Google Doc con 4 secciones:**

1. **Mi Formulario + Agente** — URL del form v0 + screenshot del flujo en Make
2. **SystemPrompt + UserPrompt** — Prompt completo (rol + categorías + reglas) + mapeo de datos
3. **Resultados de Prueba** — Tabla con 5 mensajes y clasificación
4. **Análisis Crítico** — 1 falla documentada + reflexión sobre tu trabajo

**Entrega:** Link público del Google Doc.

## 🚀 Bonus (Opcional)

1. Cambia las categorías a algo de tu trabajo real (no PetShop)
2. Ajusta el SystemPrompt con criterios de tu industria
3. Envía mensajes reales (anonimizados) desde tu form y compara
