> 📦 **Módulo 2:** Clase 1 de 4

# Clase 05: Tu Primer Agente IA

## Resumen

En el Módulo 1 aprendiste a comunicarte con la IA y a usarla como herramienta manual. En esta clase das el salto: la IA deja de ser algo que usas y se convierte en algo que **trabaja por ti**. Construirás un agente de triage — un flujo automatizado que recibe mensajes desde un formulario, los clasifica con IA y envía un email con la clasificación y acción sugerida. Es la evolución directa de lo que hiciste en Clase 02: el mismo triage, pero ahora corre solo.

La diferencia entre automatización y agente es una sola palabra: **decisión**. Una automatización sigue reglas fijas ("si llega email, reenviar a soporte"). Un agente usa IA para decidir ("si llega mensaje, IA lee el contenido, decide si es urgente/consulta/venta, y responde diferente en cada caso"). Hoy construirás tu primer agente.

```
┌──────────────┐     ┌──────────┐     ┌──────────────┐     ┌──────────┐
│ FORMULARIO   │ ──→ │ WEBHOOK  │ ──→ │  IA DECIDE   │ ──→ │  GMAIL   │
│ (v0.app)     │     │ (Make)   │     │ (OpenRouter)  │     │ (email)  │
└──────────────┘     └──────────┘     └──────────────┘     └──────────┘
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
Clase 02: Tú + Claude → Triage manual
   → Escribes prompt, pegas mensajes, lees resultado

         ↓ AHORA ↓

Clase 05: Form + Make + Grok → Triage automático
   → Mensaje llega desde formulario, IA clasifica, email se envía SOLO
```

> 💡 **El prompt que escribiste en C02 se convierte en el "cerebro" de tu agente.**

---

## 💡 El Insight Central

**Agente = Automatización que DECIDE**

```
Automatización tradicional:
   IF email llega → THEN reenviar a soporte (siempre igual)

Agente IA:
   IF mensaje llega → IA LEE → DECIDE categoría → EMAIL con clasificación
   ├── Urgente    → Email con alerta inmediata
   ├── Consulta   → Email con draft de respuesta
   └── Venta      → Email con registro de lead
```

El agente tiene 4 componentes:
1. **Entrada:** De dónde vienen los datos (formulario en v0)
2. **Trigger:** Qué lo activa (webhook en Make)
3. **Decisión:** IA que lee y clasifica (Grok vía OpenRouter — SystemPrompt + UserPrompt)
4. **Acción:** Qué hace con la decisión (email vía Gmail)

---

## ¿Qué haremos en clase?

1. **Entenderás la diferencia** — Automatización vs agente (reglas fijas vs decisión IA) con demo en vivo
2. **Crearás tu formulario con IA** — Usando v0 para generar un form profesional (refuerzo de Few-shot de C02)
3. **Construirás tu agente en Make** — Webhook → OpenRouter (SystemPrompt + UserPrompt) → Gmail
4. **Probarás con datos reales** — Enviar mensajes desde TU form y verificar clasificación en Gmail
5. **Analizarás las fallas** — Porque tu agente TAMBIÉN se va a equivocar

## 🎯 Objetivos de aprendizaje

Al finalizar esta clase, serás capaz de:

1. **Distinguir entre automatización y agente IA** — Cuándo usar reglas fijas vs decisión con IA
2. **Construir un agente funcional en Make** — Formulario + decisión IA + acción por email
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
- ¿Qué pasaría si alguien (o algo) clasificara por ti con 80% de precisión?

### 📚 Recursos opcionales

- [Make: Getting Started](https://www.make.com/en/help/tutorials){:target="_blank"} — Tutorial básico
- [OpenRouter Docs](https://openrouter.ai/docs){:target="_blank"} — Documentación de la API
- [v0.dev](https://v0.dev){:target="_blank"} — Generador de interfaces con IA (lo usaremos en clase)

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
- **Gemini**: IA de Google que usaremos como clarificador de estilo para el formulario (ya la conoces de C04)
- **SystemPrompt**: Instrucciones permanentes que definen el ROL y REGLAS del agente (lo que el agente "es")
- **UserPrompt**: Los datos específicos de cada mensaje que el agente debe procesar (lo que el agente "recibe")

---

## La Evolución desde M1

```
M1: Tú operas la IA manualmente
   Clase 01: Sistema básico → Tú escribes, IA responde
   Clase 02: RICE + Few-shot → Tú escribes mejor, IA responde mejor
   Clase 03: Socio pensante → IA pregunta, tú respondes
   Clase 04: Integración → Tú combinas herramientas

         ↓ CAMBIO DE PARADIGMA ↓

M2: La IA opera por ti
   Clase 05: Agente → La IA recibe, decide y actúa SIN que estés
```

### Refuerzo de técnicas M1

| Técnica de M1 | Cómo la usas en C05 |
|---------------|---------------------|
| Few-shot / Ejemplo (C02) | Wireframe adjunto al prompt de v0 para generar tu form |
| Socio pensante (C03) | Gemini como clarificador de estilo del formulario |
| System prompt (C01) | SystemPrompt en OpenRouter define el rol del agente |
| RICE (C02) | Estructura del UserPrompt con datos del formulario |

---

## Herramientas necesarias

- [ ] 💻 Laptop con Make y OpenRouter abiertos
- [ ] 🔑 API key de OpenRouter generada y guardada
- [ ] 📝 Prompt de triage de Clase 02 (Google Doc)
- [ ] 🖼️ Wireframe o ejemplo de formulario de contacto
- [ ] 🧠 Idea de cómo adaptarías el triage a TU trabajo
