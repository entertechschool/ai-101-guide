# Lab 07: Mi Agente Real

## Objetivo

Construir un agente de triage/clasificación para tu caso real de trabajo, clonando el patrón de C05-C06 y adaptando cada pieza a tu contexto.

> ⏱️ **Tiempo estimado:** 90 minutos

---

## Arquitectura: De PetShop a Tu Caso

```
PetShop (C06):                         Tu Caso (C07):
┌──────────┐  ┌─────────┐  ┌────────┐  ┌──────────┐  ┌─────────┐  ┌────────┐
│Form      │→ │Webhook  │→ │OpenR.  │  │Form TUYO │→ │Webhook  │→ │OpenR.  │
│PetShop   │  │(Make)   │  │URGENTE │  │(tu caso) │  │(Make)   │  │CAT1    │
└──────────┘  └─────────┘  │CONSULTA│  └──────────┘  └─────────┘  │CAT2    │
                           │VENTA   │                              │CAT3    │
                           └───┬────┘                              └───┬────┘
                               │                                       │
                    ┌──────────┼──────────┐             ┌──────────────┼──────────┐
                    │          │          │             │              │          │
                  Gmail🔴   Gmail🔵   Gmail🟢       Gmail[X]      Gmail[Y]   Gmail[Z]
                  + Sheets  + Sheets  + Sheets       + Sheets     + Sheets   + Sheets
```

---

## Antes de empezar

| ✅ | Requisito |
|----|-----------|
| | Escenario C06 con 5+ módulos funcionando en Make |
| | 5 mensajes reales de tu proceso |
| | Idea de qué clasificas manualmente en tu trabajo |
| | Claude abierto para diseñar SystemPrompt |

---

## Parte 1: Diseñar mi caso (20 min)

### 1.1 Elegir caso

Revisa estos arquetipos por industria. Si tu trabajo encaja en uno, úsalo como punto de partida:

| Industria | Caso | Categorías | Ejemplo de input |
|-----------|------|------------|------------------|
| Freelancer/Consultor | Triage de solicitudes | PROYECTO / CONSULTA / SPAM | "Hola, necesito un logo para mi empresa..." |
| Ventas/Comercial | Clasificar leads | CALIENTE / TIBIO / FRÍO | "Quiero cotización para 500 unidades" |
| Soporte/Servicio | Priorizar tickets | URGENTE / NORMAL / FAQ | "El sistema se cayó, no puedo facturar" |
| RRHH/People | Filtrar candidatos | AVANZAR / REVISAR / RECHAZAR | "5 años de experiencia en marketing..." |
| Marketing | Clasificar feedback | POSITIVO / MEJORA / QUEJA | "Me encantó el último post sobre..." |
| Educación | Triage consultas | ACADÉMICO / TÉCNICO / ADMIN | "No puedo acceder al campus virtual" |

> 💡 Si ninguno encaja: **"¿Qué haces manualmente más de 5 veces por semana que involucre decidir, clasificar o priorizar?"**

### 1.2 Definir categorías + reglas + acciones

Completa esta tabla para TU caso:

| Categoría | Regla (cuándo aplica) | Acción (qué hace el agente) |
|-----------|----------------------|----------------------------|
| [CAT1] | Cuando el mensaje... | Gmail con emoji [X] + asunto... |
| [CAT2] | Cuando el mensaje... | Gmail con emoji [Y] + asunto... |
| [CAT3] | Cuando el mensaje... | Gmail con emoji [Z] + asunto... |

### 1.3 Escribir SystemPrompt con Claude (callback C03)

Usa Claude como socio pensante. Copia y personaliza este prompt:

```
Soy [mi rol] en [mi industria].
Necesito un SystemPrompt para un agente que clasifique [tipo de mensajes].

Mis categorías:
- [CAT1]: cuando [regla]
- [CAT2]: cuando [regla]
- [CAT3]: cuando [regla]

Formato de salida obligatorio:
CATEGORÍA: [X]
RESUMEN: [1 línea]
ACCIÓN: [qué hacer]

Antes de escribir el prompt, hazme preguntas sobre casos ambiguos
que podrían confundir al agente.
```

> ✅ **Checkpoint Parte 1:** Caso definido + SystemPrompt escrito + 3 categorías con reglas claras

---

## Parte 2: Construir mi agente (50 min)

### 2.1 Clonar escenario C06 (5 min)

En Make, duplica tu escenario de PetShop:
1. Abre tu escenario de C06
2. Menú `⋯` → **Export Blueprint**
3. Crea un **nuevo escenario** → **Import Blueprint**
4. Ahora tienes una copia idéntica al agente PetShop

> ⚠️ **Si perdiste tu escenario C06:** Avisa al facilitador — tiene un escenario de backup para compartir.

### 2.2 Nuevo formulario v0 (15 min)

Crea un formulario para TU caso (igual que en C05):

1. Usa **Gemini** para scaffolding del prompt de v0
2. Campos relevantes a **tu caso** (no nombre/email de PetShop)
3. Agrega bloque debug (muestra respuesta + botón reintentar)
4. Deploy en v0 → copia la URL pública

### 2.3 Adaptar módulos en Make (25 min)

Módulo por módulo, actualiza tu escenario clonado:

**a) OpenRouter** — Reemplazar SystemPrompt completo
- Pega tu SystemPrompt nuevo (de 1.3)
- Actualiza el UserPrompt para mapear los campos de tu nuevo form

**b) Router** — Cambiar los 3 Filters
- De: `URGENTE` / `CONSULTA` / `VENTA`
- A: `[TU CAT1]` / `[TU CAT2]` / `[TU CAT3]`
- ⚠️ **EXACTO y case-sensitive** — debe coincidir con el output del SystemPrompt

**c) Gmail ×3** — Nuevos asuntos y cuerpos
- Actualiza emojis, asuntos y cuerpo de cada email según tus categorías

**d) Google Sheets** — Ajustar columnas si es necesario
- Si cambiaste campos del form, actualiza los nombres de columna

### 2.4 Conectar form al webhook (5 min)

1. Copia la URL del webhook de tu nuevo escenario
2. Pégala en el código de tu formulario v0
3. Activa el escenario en Make (toggle ON)

> ✅ **Checkpoint Parte 2:** Escenario adaptado + form nuevo conectado al webhook

---

## Parte 3: Probar + Iterar (20 min)

### 3.1 Enviar los 5 mensajes reales (5 min)

Desde tu nuevo formulario, envía tus 5 mensajes reales uno a uno. Verifica en Make History que cada uno se procese.

### 3.2 Revisar Google Sheets (5 min)

Completa esta tabla de resultados:

| # | Mensaje (resumen) | Esperado | Real | ✅/❌ |
|---|-------------------|----------|------|-------|
| 1 | ... | CAT1 | CAT1 | ✅ |
| 2 | ... | CAT2 | CAT1 | ❌ |
| 3 | ... | CAT3 | CAT3 | ✅ |
| 4 | ... | CAT1 | CAT2 | ❌ |
| 5 | ... | CAT2 | CAT2 | ✅ |

### 3.3 Iterar SystemPrompt (10 min)

Según los resultados:

- **Si clasifica todo igual** → Las reglas no son suficientemente específicas. Agrega diferenciadores.
- **Si confunde 2 categorías** → Las reglas son ambiguas entre esas categorías. Agrega ejemplos o palabras clave.
- **Si acierta todo** → Envía 2 mensajes ambiguos adicionales para estresar al agente.

Haz el cambio en el SystemPrompt → re-envía los mensajes que fallaron → verifica mejora.

> ✅ **Checkpoint Parte 3:** 5 mensajes procesados + tabla de resultados + al menos 1 mejora documentada

---

## Entregable

Agrega una nueva sección a tu Google Doc de C05+C06:

1. **Mi Caso Real** — Descripción del proceso + categorías + reglas
2. **Mi Agente Adaptado** — Screenshot de Make (escenario adaptado) + SystemPrompt nuevo completo
3. **Mi Formulario** — URL del form v0 nuevo
4. **Tabla de Resultados** — Esperado vs real para 5 mensajes
5. **Mejora Documentada** — Qué cambiaste en el SystemPrompt y por qué

**Formato:** Google Doc con link público (mismo documento de C05+C06, nueva sección "C07: Mi Agente Real")

---

## Bonus (opcional)

- Agrega una 4ta categoría a tu caso
- Crea reglas condicionales más complejas (ej: si tiene deadline + monto alto → URGENTE)
- Prueba con 10 mensajes adicionales y documenta la tasa de acierto
