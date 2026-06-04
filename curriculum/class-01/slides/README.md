<!-- .slide: data-background="#0A192F" -->

# SESIÓN 1
## PROMPTS EFECTIVOS

El arte de pedirle a la IA lo que necesitas

*Sesión 1 de 8 · 60 minutos · Online en vivo*

---

## QUÉ VAMOS A LOGRAR HOY

*Objetivo · Fundamentos · Mini-proyecto*

### OBJETIVO DE LA SESIÓN

Aplicar prompts estructurados con asistentes de IA para obtener respuestas precisas en tareas profesionales.

### FUNDAMENTOS

1. ¿Qué es un prompt?
2. Anatomía de un buen prompt
3. Formato del output: libre vs estructurado

### MINI-PROYECTO

3 prompts profesionales que resuelven tareas reales

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿Qué tareas haces todos los días que te quitan tiempo?

**02** ¿Usaste alguna vez ChatGPT, Gemini o Claude? ¿Qué tal te fue?

**03** Si la IA pudiera hacer UNA cosa por ti hoy, ¿cuál sería?

> 💡 Tus respuestas nos dicen qué casos reales atacar en las próximas 7 sesiones.

---

## FUNDAMENTO 1 · ¿QUÉ ES UN PROMPT?

*La instrucción que le das a la IA*

**Teoría**

Entrada → modelo → respuesta:

- **Tu instrucción** — lo que pides
- **Modelo de IA** — procesa
- **Respuesta** — lo que devuelve

> Mejor instrucción = mejor respuesta.

---

## FUNDAMENTO 2 · ANATOMÍA DE UN BUEN PROMPT

*Rol + Tarea + Contexto + Formato*

- 🎭 **ROL** — quién es la IA ("actúa como contador")
- 🎯 **TAREA** — qué debe hacer ("clasifica este correo")
- 🧩 **CONTEXTO** — datos relevantes ("cliente VIP, factura impaga")
- 📦 **FORMATO** — cómo lo quieres ("en 2 líneas, tono formal")

---

## EJEMPLO REAL · LAS 4 PARTES

*Clasificar un correo de cliente*

```
Actúa como asesor comercial senior.          ← ROL
Clasifica el siguiente correo en una de
estas categorías: [Venta / Queja / Consulta]. ← TAREA
El cliente es VIP y tiene una factura
impaga del mes pasado.                         ← CONTEXTO
Devuelve la categoría en 1 palabra y una
explicación de máximo 2 líneas.                ← FORMATO
```

---

## FUNDAMENTO 3 · LIBRE VS ESTRUCTURADO

*Cuando el resultado va a otra app, pide formato fijo*

| TEXTO LIBRE | ESTRUCTURADO (JSON) |
|-------------|---------------------|
| Bueno para leer | Difícil de leer |
| Difícil de procesar | Fácil de procesar |
| Para humanos | Para apps / flujos |

> Lo que en la sesión 4 va a viajar dentro de un flujo automático.

---

## EJEMPLO REAL · LA MISMA TAREA

*Texto libre vs JSON*

**Texto libre (para leer):**

> "El cliente está molesto por la demora. Recomiendo responder con disculpa y 10% de descuento."

**JSON (para procesar en Make):**

```json
{
  "categoria": "Queja",
  "urgencia": "alta",
  "accion": "disculpa + descuento 10%"
}
```

---

## MINI-PROYECTO · 3 PROMPTS PROFESIONALES

*Tareas reales de tu trabajo*

**Individual**

### QUÉ HACER

1. Elige 3 tareas reales que te quitan tiempo
2. **Prompt 1** — Clasificar un correo (rol + tarea + contexto + formato de lista)
3. **Prompt 2** — Resumir una reunión (bullets + acciones siguientes)
4. **Prompt 3** — Redactar respuesta de venta (tono profesional, 2 opciones)
5. Prueba y ajusta cada uno hasta que el output esté listo

✓ **Verificación:** 3 prompts probados y guardados para reusar

---

## LO QUE TE LLEVAS HOY

*Listo para empezar a automatizar*

**01** 3 prompts profesionales listos para usar

**02** La anatomía: Rol + Tarea + Contexto + Formato

**03** Cuándo pedir output estructurado vs libre

### PRÓXIMA SESIÓN

Sesión 2: Make 101 + Google Cloud. Metemos estos prompts dentro de un flujo automático real.
