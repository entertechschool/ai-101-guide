<!-- .slide: data-background="#0A192F" -->

# Clase 07: Mi Agente Real
## De clasificar a generar

*AI 101 - Entertech School*

---

## 🧠 Pregunta Detonadora

### ¿Qué pasa si le das a la IA tus notas de reunión tal cual?

**A)** Las organiza perfectamente en un acta ejecutiva

**B)** Las ignora porque son "muy desordenadas"

**C)** Depende de CÓMO le pidas que las procese

**D)** Necesitas limpiarlas antes de dárselas

> 🕐 30 segundos para pensar → levanten la mano

---

## 🧠 Pregunta Detonadora — Respuesta

**Respuesta correcta: C**

- **A:** ❌ Sin instrucciones claras, el resultado es genérico
- **B:** ❌ La IA sí las procesa — pero sin estructura, el output es caos también
- **C:** ✅ La clave está en el SystemPrompt: qué analizar, qué generar, en qué formato
- **D:** ❌ Justamente el poder es que la IA limpie POR TI

> **Hoy construyes un agente que toma caos y produce algo profesional. Automáticamente.**

---

## 🎬 Demo: Agente del Facilitador

### Escribo algo desordenado → me llega un email profesional.

El facilitador muestra su agente EN VIVO:

1. Abre su formulario (URL de Vercel)
2. Escribe algo desordenado en el textarea
3. Click en enviar
4. Muestra en Make cómo pasa por 5 módulos
5. Abre su correo → email profesional con formato HTML

Y después: muestra su **repo en GitHub** con los SystemPrompts documentados.

> "Esto es lo que van a construir hoy. Desde cero."

---

## De clasificar a GENERAR

### La evolución C05-C06 → C07

```
C05-C06: CLASIFICAR                   C07: GENERAR
┌──────────────────┐                  ┌──────────────────┐
│ Input             │                 │ Input             │
│ → IA clasifica    │                 │ → IA #1 ANALIZA   │
│ → Router decide   │                 │ → IA #2 GENERA    │
│ → Email etiqueta  │                 │ → Email creado    │
└──────────────────┘                  └──────────────────┘

Output: etiqueta (URGENTE)            Output: contenido (email completo)
1 IA, 1 decisión                      2 IAs encadenadas, 2 trabajos
```

> **Antes** la IA ponía una etiqueta. **Ahora** la IA crea contenido profesional.

---

## Nueva Arquitectura: 2 IAs Encadenadas

```
Form v0 (textarea + campo extra + email)
    │
    ▼
Webhook (Make)
    │
    ▼
OpenRouter #1 — ANALIZAR
(input crudo → JSON estructurado)
    │
    ├──────────────────┐
    ▼                  ▼
Google Sheets      OpenRouter #2 — GENERAR
(registra log)     (JSON → email HTML profesional)
                       │
                       ▼
                   Gmail → email al usuario
```

### 5 módulos. 2 cerebros. 1 email profesional.

---

## Los 3 Escenarios

| # | Escenario | Escribes... | Recibes... |
|---|-----------|-------------|------------|
| 1 | Clarificador de Ideas | Idea desordenada | Brief profesional |
| 2 | Notas de Reunión | Garabatos, abreviaturas | Acta ejecutiva |
| 3 | Feedback Profesional | Frustración/elogio crudo | Guía SBI para entregarlo |
| 4 | Tu propio caso | Tu input real | Tu output profesional |

> 💡 Eliges 1 escenario. O propones el tuyo con una plantilla guiada.

---

## ⚠️ Anti-Hype

### Tu agente va a generar emails mediocres al principio.

- El primer output de OR#2 probablemente sea genérico o muy largo
- Los SystemPrompts necesitan al menos 2-3 iteraciones
- El JSON de OR#1 puede venir malformado — hay que ajustar el prompt
- Gmail puede mostrar HTML como texto plano si no marcas la opción correcta

> **La habilidad no es que funcione perfecto al primer intento. Es que sepas diagnosticar y mejorar.**

---

## 🚀 Tu primer proyecto open-source

### v0 → Vercel → GitHub

```
1. Creas form en v0          → Tienes código
2. Deploy en Vercel           → Tienes URL pública
3. Connect to GitHub          → Tienes repositorio
4. Editas README en GitHub    → Documentas tus SystemPrompts
```

### ¿Por qué importa?

- **URL pública:** cualquiera puede usar tu agente
- **Repo en GitHub:** tu primer proyecto open-source
- **README con SystemPrompts:** documenta el "cerebro" de tu agente
- **Portfolio real:** lo muestras en C08 y LinkedIn

> "No es tarea. Es tu primer proyecto publicado."

---

## Lab Time

### Mi Agente Real — 60 min

| Parte | Tiempo | Qué haces |
|-------|--------|-----------|
| **1. Diseñar** | 10 min | Elegir escenario + revisar/personalizar SystemPrompts con Claude |
| **2. Construir** | 40 min | Form v0 + Make (5 módulos) + deploy Vercel + GitHub |
| **3. Documentar** | 10 min | README con SystemPrompts + test final + verificar |

> 💡 Tu experiencia de C02 + C03 + C05 + C06 = todo lo que necesitas.

---

## ✅ Checkpoints

### Parte 1 — Diseñar:
- [ ] Escenario elegido (1, 2, 3 o propio)
- [ ] 2 SystemPrompts listos (OR#1 analítico + OR#2 generativo)

### Parte 2 — Construir:
- [ ] Form v0 creado y deployado en Vercel
- [ ] Make: 5 módulos conectados (Webhook → OR#1 → Sheets → OR#2 → Gmail)
- [ ] Email llega con formato HTML
- [ ] Repo en GitHub creado

### Parte 3 — Documentar:
- [ ] README del repo con SystemPrompts documentados
- [ ] 2 mensajes enviados desde URL de Vercel
- [ ] Sheets con al menos 2 registros

---

## 📝 Entrega + Preview C08

### Tu entregable:
1. URL de Vercel (form público)
2. URL de GitHub (repo con README + SystemPrompts)
3. Screenshot de Make (5 módulos)
4. Screenshot de Sheets (2+ registros)
5. Screenshot del email recibido

### Próxima clase: Demo Day

> **Presentas TU agente EN VIVO.**
> Alguien del público abre tu URL de Vercel y envía un mensaje.
> Todos ven el email llegar en tiempo real.

---

## 💡 Reflexión

### Hoy aprendiste:
- A encadenar 2 IAs: una que analiza, otra que genera
- Que el mismo input puede producir outputs muy diferentes según el SystemPrompt
- A publicar tu primer proyecto en GitHub con documentación profesional
- Que el "cerebro" del agente son los SystemPrompts — y documentarlos es tan importante como construirlos

### La pregunta:
> "Tienes una URL pública, un repo en GitHub, y un agente que transforma caos en contenido profesional. ¿Qué otro proceso de tu trabajo podrías automatizar con este mismo patrón?"
