> 📦 **Módulo 2:** Clase 1 de 4

# Clase 05: Tu Primer Agente IA

## Resumen

En el Módulo 1 aprendiste a comunicarte con la IA y a usarla como herramienta manual. En esta clase das el salto: la IA deja de ser algo que usas y se convierte en algo que **trabaja por ti**. Construirás el cerebro de un agente de triage — un formulario con v0 que envía datos a Make, donde la IA clasifica con OpenRouter. Es la evolución directa de lo que hiciste en Clase 02: el mismo triage, pero ahora el agente piensa solo.

La diferencia entre automatización y agente es una sola palabra: **decisión**. Una automatización sigue reglas fijas ("si llega email, reenviar a soporte"). Un agente usa IA para decidir ("si llega mensaje, IA lee el contenido, decide si es urgente/consulta/venta"). Hoy construyes el cerebro. En Clase 06 le darás manos (Gmail), inteligencia (Router) y memoria (Google Sheets).

```
┌──────────────────┐     ┌──────────┐     ┌──────────────┐
│ FORMULARIO + DBG │ ──→ │ WEBHOOK  │ ──→ │  IA DECIDE   │
│ (v0.app)         │     │ (Make)   │     │ (OpenRouter)  │
└──────────────────┘     └──────────┘     └──────────────┘
```

---

## ¿Por qué te sirve?

### El problema real

Ya sabes crear prompts poderosos. Pero los ejecutas manualmente:
- Abres Claude, pegas el mensaje, lees la respuesta, tomas acción
- Repites esto 10, 20, 50 veces al día
- Tu expertise en prompting no escala si depende de TU tiempo

### Lo que cambia con esta clase

| Sin agente | Con agente |
|------------|-----------|
| Clasificas mensajes uno por uno | El agente clasifica 24/7 sin que estés |
| Tú decides la prioridad cada vez | La IA decide con TU criterio (tu prompt) |
| Tu tiempo = cuello de botella | Tu tiempo = supervisión y mejora |
| Escalas si trabajas más horas | Escalas mejorando el prompt |

### La evolución desde Clase 02

```
C02: Tú + Claude → Triage manual (pegas mensajes, lees resultado)
         ↓ AHORA ↓
C05: Form + Make + Grok → Triage automático (la IA clasifica SOLA)
```

> 💡 **El prompt de C02 se convierte en el "cerebro" de tu agente.**

---

## 💡 El Insight Central

**Agente = Automatización que DECIDE**

```
Automatización tradicional:
   IF email llega → THEN reenviar a soporte (siempre igual)

Agente IA:
   IF mensaje llega → IA LEE → DECIDE categoría → acción diferente
   ├── Urgente    → Alerta inmediata
   ├── Consulta   → Respuesta estándar
   └── Venta      → Registro de lead
```

El agente tiene 3 componentes (hoy construimos los 3):
1. **Entrada:** De dónde vienen los datos (formulario v0 con bloque debug)
2. **Trigger:** Qué lo activa (webhook en Make)
3. **Decisión:** IA que lee y clasifica (Grok vía OpenRouter — SystemPrompt + UserPrompt)

> 📌 En C06 agregamos el 4to componente: **Acción** (Gmail + Router + Google Sheets).

---

## ¿Qué haremos en clase?

1. **Entenderás la diferencia** — Automatización vs agente (reglas fijas vs decisión IA) con demo en vivo
2. **Crearás tu formulario con IA** — Scaffolding con Gemini + v0 para generar un form con bloque debug (refuerzo C02-C03)
3. **Construirás el cerebro del agente en Make** — Webhook → OpenRouter (API Key + SystemPrompt + UserPrompt)
4. **Verás al agente pensar** — Enviar mensajes desde TU form y ver clasificación en Make History

## 🎯 Objetivos de aprendizaje

Al finalizar esta clase, serás capaz de:

1. **Distinguir entre automatización y agente IA** — Cuándo usar reglas fijas vs decisión con IA
2. **Construir el cerebro de un agente en Make** — Formulario + webhook + decisión IA
3. **Identificar cuándo un agente necesita supervisión humana** — Límites de la autonomía

---

## 📌 Preparación para la clase

> **Antes de llegar a clase, prepárate:**

### ✅ Tareas previas (OBLIGATORIAS)

1. **Crear cuenta en Make** ⚠️ REQUERIDO
   - Ir a [make.com](https://make.com){:target="_blank"}
   - Crear cuenta gratuita (el plan free incluye 1,000 operaciones/mes)
   - Verificar que puedes acceder al dashboard
   - *No necesitas crear ningún escenario aún*

2. **Crear cuenta en OpenRouter** ⚠️ REQUERIDO
   - Ir a [openrouter.ai](https://openrouter.ai){:target="_blank"}
   - Crear cuenta gratuita
   - Ir a "Keys" y generar una API key
   - Guardar tu API key en lugar seguro (la usarás en clase)
   - *Usaremos Grok Free, que no tiene costo*

3. **Tener tu prompt de triage de Clase 02 a la mano**
   - El prompt RICE + Few-shot que construiste para PetShop Express
   - Será la base del "cerebro" de tu agente
   - Si no lo tienes, revisa tu Google Doc de C02

4. **Tener un wireframe o ejemplo visual de formulario de contacto**
   - Busca un formulario que te guste (puede ser screenshot de una web)
   - Lo usarás como ejemplo para que v0 genere tu form (Few-shot visual, como en C02)
   - Si no tienes uno, el facilitador compartirá un wireframe base

### 🧠 Reflexiona sobre esto

- ¿Qué tareas repites diariamente que siguen un patrón de clasificar + actuar?
- ¿Cuántos mensajes/emails clasificas manualmente por semana?

### 📚 Recursos opcionales

- [Make: Getting Started](https://www.make.com/en/help/tutorials){:target="_blank"}
- [OpenRouter Docs](https://openrouter.ai/docs){:target="_blank"}
- [v0.dev](https://v0.dev){:target="_blank"} — Generador de interfaces con IA

---

## Glosario de nuevos términos

- **Agente IA**: Flujo automatizado que usa inteligencia artificial para tomar decisiones, no solo seguir reglas fijas
- **Make**: Plataforma visual de automatización no-code (antes conocida como Integromat)
- **Trigger**: Evento que inicia un flujo automatizado (llegada de datos, webhook, horario programado)
- **OpenRouter**: Plataforma que da acceso a múltiples modelos de IA a través de una sola API
- **Grok**: Modelo de IA creado por xAI, disponible gratis a través de OpenRouter
- **Webhook**: URL única que recibe datos automáticamente cuando ocurre un evento externo
- **API Key**: Contraseña que identifica tu cuenta al usar una API
- **v0**: Herramienta de Vercel que genera interfaces web (formularios, páginas) a partir de un prompt
- **Bloque debug**: Panel en el formulario que muestra la respuesta del servidor y permite reintentar
- **Gemini**: IA de Google que usaremos como scaffolding para el prompt de v0 (ya la conoces de C04)
- **SystemPrompt**: Instrucciones permanentes que definen el ROL y REGLAS del agente (lo que el agente "es")
- **UserPrompt**: Los datos específicos de cada mensaje que el agente debe procesar (lo que el agente "recibe")

---

## Herramientas necesarias

- [ ] 💻 Laptop con Make y OpenRouter abiertos
- [ ] 🔑 API key de OpenRouter generada y guardada
- [ ] 📝 Prompt de triage de Clase 02 (Google Doc)
- [ ] 🖼️ Wireframe o ejemplo de formulario de contacto
- [ ] 🧠 Idea de cómo adaptarías el triage a TU trabajo
