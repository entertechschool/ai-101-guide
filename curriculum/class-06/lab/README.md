# Lab 06: Mi Agente Inteligente

En C05 construiste el cerebro. Hoy le das manos (Gmail), inteligencia (Router) y memoria (Google Sheets). Al final, compites: ¿quién tiene el mejor agente de triage?

> ⏱️ **Tiempo:** 95 minutos

### 🎯 Objetivo

Completar el agente de C05 con Gmail, expandirlo con Router (3 rutas) y Google Sheets (logging), y competir en un battle de clasificación.

## Arquitectura Final

```
                                    ┌─ 🔴 URGENTE → Gmail rojo → Sheets
Form → Webhook → OpenRouter → Router├─ 🔵 CONSULTA → Gmail normal → Sheets
                                    └─ 🟢 VENTA → Gmail verde → Sheets
```

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Escenario de C05 en Make | Webhook → OpenRouter funcionando |
| URL de tu formulario v0 | Accesible y conectado al webhook |
| Google Sheets nueva | Vacía, lista para configurar |
| SystemPrompt de C05 | En tu Google Doc |

---

## Parte 1: Completa tu Agente — El Momento WOW (20 min)

### 1.1 Abre tu escenario de C05

En Make, abre tu escenario: `Webhook → OpenRouter`. Verifica que funcione enviando 1 mensaje de prueba.

> Si no lo tienes, el facilitador te dará acceso a un template actualizado.

### 1.2 Agrega módulo Gmail

Haz clic en el **+** después de OpenRouter y agrega el módulo **Gmail > Send an Email**:

1. **Conectar cuenta Gmail** — Autoriza permisos cuando Make lo pida
2. **Para:** Tu email personal
3. **Asunto:** `[{{CATEGORÍA}}] Nuevo mensaje de {{nombre}}`
4. **Cuerpo:** La clasificación completa de OpenRouter (mapea el output)

### 1.3 Activa y prueba

1. Activa el escenario (switch **ON**)
2. Envía 2 mensajes desde TU formulario v0
3. Revisa tu Gmail — deberías tener 2 emails con clasificación

### WOW moment

> Tu agente recibió un mensaje, lo clasificó y te avisó por email. Sin que hicieras nada.

✅ **Checkpoint:** 2 emails recibidos en Gmail con clasificación del agente.

---

## Parte 2: Agente Inteligente — Router + Google Sheets (35 min)

### 2.1 Concepto: flujo lineal vs branching (5 min)

El facilitador explica la diferencia:

```
Lineal:    Webhook → OpenRouter → Gmail (siempre el mismo email)
Branching: Webhook → OpenRouter → Router → [URGENTE → Gmail rojo]
                                           [CONSULTA → Gmail normal]
                                           [VENTA → Gmail verde]
```

### 2.2 Agregar Router (10 min)

1. En Make, haz clic derecho en la conexión entre OpenRouter y Gmail
2. Selecciona **Add a Router**
3. Crea 3 rutas con **Filters**:
   - **Ruta 1 — URGENTE**: Filter → output contains "URGENTE"
   - **Ruta 2 — CONSULTA**: Filter → output contains "CONSULTA"
   - **Ruta 3 — VENTA**: Filter → output contains "VENTA"
4. Cada ruta conecta a un módulo Gmail con asunto diferente:
   - 🔴 `[URGENTE] Nuevo mensaje de {{nombre}}`
   - 🔵 `[CONSULTA] Nuevo mensaje de {{nombre}}`
   - 🟢 `[VENTA] Nuevo mensaje de {{nombre}}`

> 💡 Si te sobra un Gmail del paso anterior, reúsalo para una de las rutas.

### 2.3 Agregar Google Sheets — Logging (15 min)

1. Agrega módulo **Google Sheets > Add a Row** a una o más rutas
2. Conecta tu cuenta de Google cuando lo pida
3. Selecciona tu hoja de Google Sheets
4. Mapea las columnas:

| Columna | Dato |
|---------|------|
| A - Timestamp | `{{now}}` |
| B - Nombre | `{{nombre}}` |
| C - Email | `{{email}}` |
| D - Mensaje | `{{mensaje}}` |
| E - Categoría | Categoría del output de OpenRouter |
| F - Acción | Acción sugerida del output |

> 💡 Puedes conectar Sheets a todas las rutas o solo a la que quieras monitorear.

### 2.4 Test completo (5 min)

Envía 3 mensajes desde tu formulario (1 urgente, 1 consulta, 1 venta):

- [ ] ¿Cada email tiene el emoji correcto en el asunto?
- [ ] ¿Google Sheets registró los 3 mensajes?
- [ ] ¿El Router ejecutó rutas diferentes?

Toma screenshot del Router con las 3 rutas ejecutadas.

✅ **Checkpoint:** Router con 3 rutas funcionando + Google Sheets registrando.

---

## Parte 3: Battle — ¿Quién Clasifica Mejor? (25 min)

### Las reglas

Todos envían los **MISMOS 5 mensajes** de PetShop Express desde su formulario:

1. "Mi perro necesita dieta especial y el pedido lleva 3 días de retraso"
2. "¿Tienen rascadores para gatos grandes? Busco uno resistente"
3. "QUIERO MI REEMBOLSO. Llevo 5 días esperando respuesta"
4. "Tengo una factura pendiente, no es urgente pero vence el viernes"
5. "Las vitaminas que compré no le hicieron efecto a mi gato"

### Comparación

Revisa tu Google Sheets y completa la tabla:

| # | Mensaje (resumen) | Tu clasificación | ¿Correcta? |
|---|-------------------|-----------------|------------|
| 1 | Perro dieta especial | | |
| 2 | Rascador para gatos | | |
| 3 | Cliente enojado reembolso | | |
| 4 | Factura "no urgente" | | |
| 5 | Vitaminas no funcionaron | | |

### Votación

- ¿Quién acertó más clasificaciones?
- ¿Qué SystemPrompt tuvo mejor resultado?
- Votan el mejor SystemPrompt del grupo

> 💡 **La lección:** el prompt define la calidad, no el modelo. Todos usan Grok, pero los resultados son diferentes.

✅ **Checkpoint:** 5 mensajes enviados, resultados comparados, votación completada.

---

## Parte 4: Análisis + Entregable (15 min)

### Documenta en Google Doc

Agrega estas secciones a tu Google Doc de C05:

**4. Resultados Battle** — Tabla con 5 mensajes y clasificación + puntuación

**5. Mi Agente Completo** — Screenshot del escenario completo en Make (5 módulos: Webhook → OpenRouter → Router → Gmail×3 + Sheets)

**6. Mi Data Log** — Screenshot de Google Sheets con registros

**7. Análisis Crítico:**

```
FALLA DEL AGENTE:
- Mensaje #: ___
- Qué hizo: ___
- Qué debería haber hecho: ___
- Causa probable: ___
- Cómo mejoraría el SystemPrompt: ___
```

**Reflexión:** ¿Qué proceso de TU trabajo sería un agente como este?

---

## 📝 Entregable Completo (C05 + C06)

**Google Doc con 7 secciones:**

1. **Mi Formulario** — URL del form v0 + screenshot (con bloque debug)
2. **Mi Agente (cerebro)** — SystemPrompt + UserPrompt completos
3. **Primer Test (C05)** — Screenshot de Make History
4. **Resultados Battle** — Tabla 5 mensajes + clasificación + puntuación
5. **Mi Agente Completo** — Screenshot Make (5+ módulos) con Router
6. **Mi Data Log** — Screenshot de Google Sheets con registros
7. **Análisis Crítico** — 1 falla documentada + reflexión

**Entrega:** Link público del Google Doc.
