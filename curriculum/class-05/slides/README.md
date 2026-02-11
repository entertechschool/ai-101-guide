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
- La IA te **conoce** (Clase 06)
- Demuestras lo que lograste (Clase 07-08)

> "M1 fue aprender a conducir. M2 es poner el piloto automático."

---

## 🧠 Pregunta Detonadora

### ¿Cuál es la diferencia entre automatización y un agente IA?

**A)** Un agente es más rápido que una automatización

**B)** Un agente usa IA para tomar decisiones, no solo seguir reglas

**C)** Un agente puede conectar más herramientas

**D)** No hay diferencia, son lo mismo

> 🕐 30 segundos para pensar → levanten la mano

---

## 🧠 Pregunta Detonadora — Respuesta

**Respuesta correcta: B**

### Análisis:

- **A:** ❌ La velocidad no es la diferencia — ambos pueden ser rápidos
- **B:** ✅ El agente DECIDE. La automatización solo ejecuta reglas fijas
- **C:** ❌ Ambos pueden conectar múltiples herramientas
- **D:** ❌ La diferencia es fundamental: reglas fijas vs decisión inteligente

> **Regla memorable:** Automatización = IF/THEN fijo. Agente = IA DECIDE el THEN.

---

## La Evolución desde Clase 02

### Clase 02: Triage MANUAL
```
Tú abres Claude
   → Pegas los mensajes
      → Lees la clasificación
         → Tú tomas la acción
```

### Clase 05: Triage AUTOMÁTICO
```
Mensaje llega desde formulario (v0)
   → Webhook lo recibe (Make)
      → IA lo clasifica (OpenRouter/Grok)
         → Email se envía solo (Gmail)
```

> **El mismo prompt de C02 se convierte en el cerebro del agente.**

---

## 🎬 Demo: Agente de Triage en Vivo

### El facilitador envía 3 mensajes desde un formulario:

**Mensaje 1:** "Mi pedido no ha llegado y es regalo de cumpleaños para mañana"

**Mensaje 2:** "¿Tienen descuento por volumen para compra corporativa?"

**Mensaje 3:** "QUIERO MI REEMBOLSO. Llevo 5 días esperando."

### Observen qué pasa:
- ¿Cada mensaje recibe un email diferente?
- ¿La categoría fue correcta?
- ¿La acción sugerida tiene sentido?

> 🎬 **Demo en vivo** — Form v0 + Make + Grok vía OpenRouter + Gmail

---

## 🎯 COMPROBACIÓN

### El agente clasificó "QUIERO MI REEMBOLSO" como urgente. ¿Es correcto?

**A)** Sí, el tono agresivo indica urgencia real

**B)** No necesariamente, el tono no siempre indica urgencia real

**C)** Sí, siempre que el cliente esté enojado es urgente

**D)** Depende del modelo de IA que uses

> 🕐 30 segundos para pensar → levanten la mano

---

## 🎯 COMPROBACIÓN — Respuesta

**Respuesta correcta: B**

### Análisis:

- **A:** ❌ Tono agresivo ≠ urgencia real (lección de C02)
- **B:** ✅ El pedido de cumpleaños tiene urgencia temporal REAL. El reembolso es importante pero no tan inmediato
- **C:** ❌ Clientes enojados merecen atención, pero la prioridad depende del impacto real
- **D:** ❌ El modelo importa, pero el PROMPT es lo que define los criterios

> **Misma lección de C02, ahora aplicada a un agente.** El prompt define la calidad de la decisión.

---

## Concepto Clave: Arquitectura del Agente

```
┌──────────────┐     ┌──────────┐     ┌──────────────┐     ┌──────────┐
│ FORMULARIO   │ ──→ │ WEBHOOK  │ ──→ │  IA DECIDE   │ ──→ │  GMAIL   │
│ (v0.app)     │     │ (Make)   │     │ (OpenRouter)  │     │ (email)  │
└──────────────┘     └──────────┘     └──────────────┘     └──────────┘
```

| Componente | Pregunta clave | Ejemplo |
|------------|---------------|---------|
| **Formulario** | ¿De dónde vienen los datos? | v0 form deployado |
| **Webhook** | ¿Qué activa el flujo? | URL de Make |
| **Decisión** | ¿Qué criterio usa? | SystemPrompt + UserPrompt |
| **Acción** | ¿Qué hace con la decisión? | Email vía Gmail |

### El prompt es el cerebro. El email es la mano.

---

## v0: Tu Formulario con IA

### ¿Qué es v0?
- Herramienta de Vercel que genera interfaces web desde un prompt
- Escribe qué quieres → v0 lo genera → Deploy con un clic

### ¿Por qué lo usamos?
- Necesitamos un origen de datos real (no curl ni JSON manual)
- Refuerza **Few-shot de C02**: adjuntas un wireframe como ejemplo
- Refuerza **Socio pensante de C03**: Gemini te ayuda a clarificar el estilo

### Refuerzo de M1 en acción:

| Técnica M1 | Cómo la usas aquí |
|------------|-------------------|
| Few-shot (C02) | Wireframe adjunto al prompt de v0 |
| Socio pensante (C03) | Gemini como clarificador de estilo |
| System prompt (C01) | SystemPrompt en OpenRouter |
| RICE (C02) | Estructura del UserPrompt |

---

## SystemPrompt vs UserPrompt

### SystemPrompt — Lo que el agente "ES"
```
Eres un agente de triage para PetShop Express.
Clasifica cada mensaje en: URGENTE, CONSULTA o VENTA.
REGLAS: Tono agresivo NO es urgencia...
```
→ Define ROL + REGLAS + CATEGORÍAS
→ Es permanente (no cambia entre mensajes)

### UserPrompt — Lo que el agente "RECIBE"
```
Nuevo mensaje de: María López
Email: maria@email.com
Mensaje: Mi perro necesita dieta especial...
```
→ Mapea los datos del formulario
→ Cambia con cada mensaje entrante

### La combinación es clave:
**Buen SystemPrompt + Buenos datos = Buena decisión**

---

## Las Herramientas de Hoy

| Herramienta | Rol | Costo |
|-------------|-----|-------|
| **v0** | Generar formulario con IA | Free (con cuenta) |
| **Make** | Plataforma de automatización visual | Free (1,000 ops/mes) |
| **OpenRouter** | Puerta a múltiples modelos de IA | Free (con Grok) |
| **Grok** | Modelo de IA que toma la decisión | Free vía OpenRouter |
| **Gmail** | Enviar email con clasificación | Tu cuenta de Google |
| **Gemini** | Clarificador de estilo (ya conocida) | Free |

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

**Objetivo:** Crear un agente: Form v0 → Webhook Make → OpenRouter/Grok → Gmail

**Partes:**
1. Concepto — Agente vs automatización (15 min)
2. Crear formulario con v0 — Few-shot + Gemini (30 min)
3. Construir agente en Make — SystemPrompt + UserPrompt + Gmail (35 min)
4. Probar con 5 mensajes desde tu form (15 min)
5. Análisis crítico — 1 falla documentada (10 min)

> 💡 Tip: Tu prompt de C02 es tu punto de partida para el SystemPrompt

---

## ✅ Checkpoint: Parte 1-2

### Verifica:
- [ ] Entiendes la diferencia entre automatización y agente
- [ ] Formulario creado en v0 y deployado
- [ ] URL del formulario copiada

**Pregunta:** ¿Usaste tu wireframe como ejemplo para v0?

---

## ✅ Checkpoint: Parte 3

### Verifica:
- [ ] Template clonado en Make (3 módulos: Webhook → OpenRouter → Gmail)
- [ ] SystemPrompt personalizado (rol + categorías + reglas)
- [ ] UserPrompt configurado con datos del formulario
- [ ] Gmail apuntando a tu email

**Pregunta:** ¿Tu SystemPrompt tiene regla para deadlines ocultos?

---

## ✅ Checkpoint: Parte 4-5

### Verifica:
- [ ] 5 mensajes enviados desde tu formulario
- [ ] 5 emails recibidos en Gmail con clasificación
- [ ] Resultados documentados en tabla
- [ ] 1 falla identificada y documentada

**Pregunta para compartir:** ¿Qué error encontraste? ¿Cómo mejorarías el SystemPrompt?

---

## 💡 Reflexión

### Hoy aprendiste:
- La diferencia entre automatización y agente IA
- Cómo crear un formulario profesional con v0 (refuerzo M1)
- Cómo construir un agente con Make + OpenRouter + Grok + Gmail
- Que SystemPrompt + UserPrompt definen la calidad de la decisión
- Que los agentes necesitan supervisión continua

### La pregunta clave:
¿Qué proceso de TU trabajo podría ser un agente como el que construiste hoy?

---

## 📝 Entrega + Preview

### Tu entregable:
1. **Mi formulario + agente** — URL del form v0 + screenshot del flujo en Make
2. **SystemPrompt + UserPrompt** — Prompts completos y documentados
3. **Resultados** — Tabla con 5 mensajes y clasificación
4. **Análisis** — 1 falla + reflexión sobre tu trabajo

**Formato:** Google Doc con link público

### Próxima clase: Tu Segundo Cerebro con IA
De un agente que clasifica mensajes → a una IA que conoce TODO tu contexto profesional
