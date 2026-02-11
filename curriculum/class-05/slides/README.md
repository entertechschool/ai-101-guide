<!-- .slide: data-background="#0A192F" -->

# Clase 05: Tu Primer Agente IA
## De ejecutar prompts a delegar decisiones

*AI 101 - Entertech School*

---

## 🔗 Transición: M1 → M2

### En el Módulo 1:
- Construiste sistemas, prompts y frameworks
- Aprendiste a comunicarte con la IA
- **Tú operabas la IA manualmente**

### En el Módulo 2:
- La IA trabaja **POR ti** (hoy)
- La IA se vuelve **inteligente** (Clase 06)
- Demuestras lo que lograste (Clase 07-08)

> "M1 fue aprender a conducir. M2 es poner el piloto automático."

---

## 🧠 Pregunta Detonadora 1

### ¿Cuál es la diferencia entre automatización y un agente IA?

**A)** Un agente es más rápido que una automatización

**B)** Un agente usa IA para tomar decisiones, no solo seguir reglas

**C)** Un agente puede conectar más herramientas

**D)** No hay diferencia, son lo mismo

> 🕐 30 segundos para pensar → levanten la mano

---

## 🧠 Pregunta Detonadora 1 — Respuesta

**Respuesta correcta: B**

- **A:** ❌ La velocidad no es la diferencia — ambos pueden ser rápidos
- **B:** ✅ El agente DECIDE. La automatización solo ejecuta reglas fijas
- **C:** ❌ Ambos pueden conectar múltiples herramientas
- **D:** ❌ La diferencia es fundamental: reglas fijas vs decisión inteligente

> **Regla memorable:** Automatización = IF/THEN fijo. Agente = IA DECIDE el THEN.

---

## 🧠 Pregunta Detonadora 2

### Imagina que recibes 100 mensajes al día.
### Con tu prompt manual de C02, ¿cuánto te toma clasificarlos?

**A)** Lo mismo que con un agente — la IA siempre tarda igual

**B)** El agente los clasifica en minutos, yo tardaría horas

**C)** El agente clasifica rápido, pero necesito revisar cada uno

**D)** B y C — clasifica rápido pero necesita supervisión

> 🕐 30 segundos → levanten la mano

---

## 🧠 Pregunta Detonadora 2 — Respuesta

**Respuesta correcta: D**

- **A:** ❌ Con prompt manual TÚ eres el cuello de botella (copiar, pegar, leer, actuar)
- **B:** ⚠️ Cierto a medias — sí es más rápido, pero...
- **C:** ⚠️ Cierto a medias — necesita supervisión, pero no cada uno
- **D:** ✅ El agente escala la velocidad, pero la supervisión no es opcional

> **Escala + supervisión.** Un agente no reemplaza tu criterio — lo multiplica.

---

## 🎬 Demo: Agente de Triage en Vivo

### El facilitador envía 3 mensajes desde un formulario:

**Mensaje 1:** "Mi pedido no ha llegado y es regalo de cumpleaños para mañana"

**Mensaje 2:** "¿Tienen descuento por volumen para compra corporativa?"

**Mensaje 3:** "QUIERO MI REEMBOLSO. Llevo 5 días esperando."

### Observen en Make History:
- ¿Cada mensaje recibió una clasificación diferente?
- ¿La categoría fue correcta?
- ¿La acción sugerida tiene sentido?

> 🎬 **Demo en vivo** — Form v0 + Make + Grok vía OpenRouter

---

## Concepto Clave: Arquitectura del Agente

```
┌──────────────────┐     ┌──────────┐     ┌──────────────┐
│ FORMULARIO + DBG │ ──→ │ WEBHOOK  │ ──→ │  IA DECIDE   │
│ (v0.app)         │     │ (Make)   │     │ (OpenRouter)  │
└──────────────────┘     └──────────┘     └──────────────┘
```

| Componente | Pregunta clave | Ejemplo |
|------------|---------------|---------|
| **Formulario** | ¿De dónde vienen los datos? | v0 form + bloque debug |
| **Webhook** | ¿Qué activa el flujo? | URL de Make |
| **Decisión** | ¿Qué criterio usa? | SystemPrompt + UserPrompt |

### Hoy construimos el cerebro. En C06 le damos manos.

---

## Las Herramientas de Hoy

| Herramienta | Rol | Costo |
|-------------|-----|-------|
| **v0** | Generar formulario con IA + bloque debug | Free (con cuenta) |
| **Make** | Plataforma de automatización visual | Free (1,000 ops/mes) |
| **OpenRouter** | Puerta a múltiples modelos de IA | Free (con Grok) |
| **Grok** | Modelo de IA que toma la decisión | Free vía OpenRouter |
| **Gemini** | Scaffolding del prompt de v0 (ya conocida) | Free |

### ¿Por qué no Claude directamente?
- Claude es más poderoso pero requiere cuenta de pago para API
- Grok Free te permite experimentar sin costo
- **Si dominas el prompt, dominas cualquier modelo**

---

## ⚠️ Las Limitaciones (Anti-Hype)

### 4 verdades sobre agentes IA:

**1. Basura entra, basura sale**
> Un agente con mal SystemPrompt comete errores... automáticamente y a escala

**2. La IA no tiene sentido común**
> "No es urgente" + deadline del viernes = la IA puede ignorar el deadline

**3. Supervisión no es opcional**
> Un agente de triage NO reemplaza a un humano. Prioriza el trabajo del humano

**4. Automatizar un mal proceso = errores más rápidos**
> Si tu triage manual es malo, el agente automático será malo... más rápido

### La fórmula real:
**Agente útil = Buen SystemPrompt + Buena supervisión + Mejora continua**

---

## Lab Time

### Mi Agente de Triage

**Objetivo:** Crear el cerebro del agente: Form v0 → Webhook Make → OpenRouter/Grok

**Tiempo:** 90 min

**Partes:**
1. Concepto — Agente vs automatización + preguntas detonadoras (15 min)
2. Crear formulario con v0 — Scaffolding Gemini + Few-shot + Debug (30 min)
3. Construir agente en Make — API Key + SystemPrompt + UserPrompt (35 min)
4. Primer test — Ver al agente pensar en Make History (10 min)

> 💡 Tip: Tu prompt de C02 es tu punto de partida para el SystemPrompt

---

## ✅ Checkpoints

### Parte 1-2:
- [ ] Entiendes la diferencia entre automatización y agente
- [ ] Formulario creado en v0 con bloque debug y deployado
- [ ] URL del formulario copiada

### Parte 3:
- [ ] Template clonado en Make (2 módulos: Webhook → OpenRouter)
- [ ] API Key de OpenRouter conectada (checkmark verde)
- [ ] SystemPrompt + UserPrompt personalizados

### Parte 4:
- [ ] Al menos 2 mensajes enviados desde tu formulario
- [ ] Clasificaciones visibles en Make History
- [ ] Screenshot tomado para el entregable

---

## 💡 Reflexión

### Hoy aprendiste:
- La diferencia entre automatización y agente IA
- Cómo crear un formulario profesional con v0 + bloque debug
- Cómo construir el cerebro de un agente en Make + OpenRouter
- Que SystemPrompt + UserPrompt definen la calidad de la decisión
- Que los agentes necesitan supervisión continua

### La pregunta clave:
¿Qué proceso de TU trabajo podría ser un agente como el que construiste hoy?

---

## 📝 Entrega + Preview

### Tu entregable (parcial — se completa en C06):
1. **Mi Formulario** — URL del form v0 + screenshot con bloque debug
2. **Mi Agente (cerebro)** — Screenshot Make (2 módulos) + SystemPrompt
3. **Primer Test** — Screenshot de Make History con clasificación

**Formato:** Google Doc con link público

### Próxima clase: Tu Agente Inteligente
Completamos el agente con Gmail + Router + Google Sheets. Y battle: ¿quién clasifica mejor?
