<!-- .slide: data-background="#0A192F" -->

# Clase 06: Tu Agente Inteligente
## De flujo lineal a agente que decide, actúa y registra

*AI 101 - Entertech School*

---

## 🔗 Transición: C05 → C06

### En Clase 05:
- Construiste el **cerebro** del agente
- Form → Webhook → OpenRouter (clasifica)
- Veías el resultado en Make History

### Hoy en Clase 06:
- Le damos **manos** (Gmail)
- Le damos **inteligencia** (Router — rutas diferentes)
- Le damos **memoria** (Google Sheets — registra todo)

> "El cerebro ya piensa. Hoy le damos cuerpo."

---

## 🧠 Pregunta Detonadora

### Tu agente clasifica todo. Pero ¿qué pasa si URGENTE y CONSULTA reciben el MISMO email?

**A)** No importa, lo importante es que clasifique

**B)** El agente debería enviar emails diferentes según la categoría

**C)** Solo necesito saber la categoría, el email es secundario

**D)** Debería enviar email diferente Y registrar la decisión

> 🕐 30 segundos → levanten la mano

---

## 🧠 Pregunta Detonadora — Respuesta

**Respuesta correcta: D**

- **A:** ❌ Si todo recibe el mismo email, ¿para qué clasificar?
- **B:** ⚠️ Cierto pero incompleto — emails diferentes es solo la mitad
- **C:** ❌ Sin acción, la clasificación no sirve de nada
- **D:** ✅ Acción diferenciada + registro = agente inteligente completo

> **Hoy:** Rutas diferentes (Router) + registro de decisiones (Google Sheets)

---

## 🎬 Demo: Completar el Agente

### El facilitador agrega Gmail al escenario de C05:

1. Envía un mensaje desde el formulario
2. El agente clasifica con OpenRouter
3. **Gmail envía un email con la clasificación**

### El momento WOW:

> "El agente recibió, pensó y te avisó. Sin que hicieras nada."

Tu primer agente end-to-end: Form → Decide → Actúa.

---

## Concepto Clave: Flujo Lineal vs Branching

```
LINEAL (C05):
  Webhook → OpenRouter → Gmail
  (todos los mensajes → mismo email)

BRANCHING (C06):
  Webhook → OpenRouter → Router ─┬─ 🔴 URGENTE → Gmail rojo
                                  ├─ 🔵 CONSULTA → Gmail normal
                                  └─ 🟢 VENTA → Gmail verde + Sheets
```

| Concepto | Qué es | Para qué |
|----------|--------|----------|
| **Router** | Divide el flujo en rutas | Acciones diferentes por categoría |
| **Filter** | Condición de cada ruta | "Si output contiene URGENTE → ruta 1" |
| **Logging** | Registrar en Sheets | Auditar decisiones del agente |

---

## ¿Por qué registrar decisiones?

### Google Sheets como bitácora del agente

**Sin logging:**
- "Mi agente clasifica bien" → ¿Cómo lo sabes?
- "El agente se equivocó" → ¿Cuántas veces? ¿En qué?

**Con logging:**
- Cada decisión queda registrada con timestamp
- Puedes auditar, filtrar, analizar tendencias
- Base para mejorar el SystemPrompt con datos reales

> **Logging no es opcional** — es lo que convierte un agente en algo profesional.

---

## Las Herramientas de Hoy

| Herramienta | Rol | Nueva? |
|-------------|-----|--------|
| **Gmail (en Make)** | Enviar emails con clasificación | Módulo nativo Make |
| **Router (en Make)** | Crear rutas condicionales | Módulo nativo Make |
| **Google Sheets (en Make)** | Registrar decisiones | ✅ Nueva |
| **Make** | Plataforma de automatización | Ya conocida (C05) |
| **OpenRouter** | IA que clasifica | Ya conocida (C05) |

### 1 herramienta nueva (Google Sheets en Make), el resto es expansión de C05.

---

## ⚠️ Las Limitaciones (Anti-Hype)

### Router no es magia:

**1. Basura en Filters = rutas equivocadas**
> Si tu Filter dice "contains URGENTE" pero tu SystemPrompt produce "Urgente", no matchea

**2. Google Sheets no es un dashboard automático**
> Registra datos, pero analizarlos sigue siendo tu trabajo

**3. El Router es tan bueno como el SystemPrompt**
> Si el SystemPrompt produce categorías inconsistentes, el Router no puede arreglarlo

**4. Más módulos = más puntos de falla**
> Cada conexión nueva es una oportunidad para que algo se rompa

### La fórmula:
**Agente inteligente = Buen SystemPrompt + Filters exactos + Supervisión**

---

## Lab Time

### Mi Agente Inteligente

**Objetivo:** Completar agente con Gmail + expandir con Router + Sheets + Battle

**Tiempo:** 95 min

**Partes:**
1. Completa tu agente — Gmail = momento WOW (20 min)
2. Agente inteligente — Router + Google Sheets (35 min)
3. Battle — ¿Quién clasifica mejor? (25 min)
4. Análisis + entregable (15 min)

> 💡 Tip: Asegúrate de que tu SystemPrompt produce categorías EXACTAS (URGENTE, CONSULTA, VENTA) para que los Filters funcionen.

---

## ⚔️ Battle Time

### Reglas:
- Todos envían los **MISMOS 5 mensajes** de PetShop Express
- Comparan resultados en Google Sheets
- ¿Quién acertó más clasificaciones?
- Votan el **mejor SystemPrompt** del grupo

### La lección:
> Mismo modelo (Grok), mismos mensajes. La diferencia está en el **SystemPrompt**.

---

## 📝 Entrega + Preview

### Tu entregable completo (C05 + C06):
1. **Mi Formulario** — URL form v0 + screenshot con debug
2. **Mi Agente Completo** — Screenshot Make (5+ módulos) + SystemPrompt + UserPrompt
3. **Resultados Battle** — Tabla 5 mensajes + clasificación + puntuación
4. **Mi Data Log** — Screenshot de Google Sheets con registros
5. **Análisis** — 1 falla documentada + reflexión

**Formato:** Google Doc con link público

### Próxima clase: Mi Agente Real
Tomas el patrón de PetShop y construyes un agente para TU caso real de trabajo.
