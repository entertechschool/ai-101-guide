# Lab 06: Integración total y mejores prácticas

## 🎯 Objetivos

1. Optimizar al menos 3 prompts aplicando persona + few-shot + chain-of-thought, documentando antes/después.
2. Aplicar las 4 mejores prácticas del sistema: nombre con fecha, carpeta Backups, error handler, pestaña Logs.
3. Definir 5 puntos críticos de personalización para Clase 7 y actualizar tabla de parámetros para tu caso real.

---

## 🔑 Conceptos Clave

- **Prompt engineering avanzado** — 3 técnicas: persona, few-shot, chain-of-thought.
- **Storytelling de datos** — contexto + causa + acción convierten cifras en historias.
- **Sistema de producción** — tiene backups, alertas y logs; no solo "funciona en demo".

---

## ⚙️ Setup Inicial

Verifica que tu sistema modelo esté activo:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Escenario 1 activo con Gemini | De Clase 5 |
| ☐ | Escenario 2 scheduled viernes con Gemini | De Clase 5 |
| ☐ | Screenshots de insights de ayer | Para comparar antes/después hoy |
| ☐ | Brief original de Clase 1 | Para revisitar al definir personalización |

---

## Actividad 1: Optimiza prompts para storytelling (45 min)

### 1.1 Analiza la diferencia entre insight plano y potente

Compará estos 3 ejemplos:

| Tipo | Insight |
|------|---------|
| **Plano** | "Las ventas de la semana fueron S/ 21,700." |
| **Mediocre** | "Las ventas fueron S/ 21,700, un 108% de la meta semanal." |
| **Potente** | "Las ventas generaron S/ 21,700 (108% de meta, +12% vs semana anterior), impulsadas por 2 renovaciones grandes de consultoría de Juan. Acción: replicar su estrategia con el resto del equipo." |

Identifica qué hace potente al tercero:
- Números concretos ✅
- Comparación (vs meta y vs anterior) ✅
- Explicación de causa ✅
- Acción sugerida ✅

### 1.2 Reescribe 3 prompts con optimización

Toma el prompt de insights de Clase 5 y reescríbelo con las 3 técnicas:

**Prompt v1 (el de ayer):**

```
Eres un analista de ventas. Analiza los datos de esta semana y devuelve JSON con:
{resumen, hallazgo_1, hallazgo_2, hallazgo_3, riesgo_1, oportunidad_1, accion_1}
DATOS: {datos_semana}
```

**Prompt v2 (optimizado):**

```
Eres un analista de ventas senior con 10 años de experiencia en consultoría.
Tu estilo es directo, basado en datos y siempre accionable.

CONTEXTO DEL NEGOCIO:
- Meta semanal: {{meta}}
- Ticket objetivo: {{ticket_objetivo}}
- Semana anterior: {{ventas_anterior}}

REGLAS DEL ANÁLISIS:
1. Cada hallazgo DEBE comparar contra meta o semana anterior
2. Cada hallazgo DEBE incluir números específicos
3. Cada hallazgo DEBE explicar la causa probable basándote en las descripciones
4. Cada acción DEBE ser ejecutable en la próxima semana (no vaga)

EJEMPLO de buen hallazgo (few-shot):
"Juan generó 45% de las ventas semanales (+22% vs su promedio),
impulsado por 2 renovaciones grandes de consultoría de larga data.
Acción: programar 1:1 con Juan para documentar qué hizo distinto y replicarlo."

DATOS SEMANA:
{{datos_formateados}}

INSTRUCCIONES:
Piensa paso a paso antes de responder:
1. Primero identifica los 3 fenómenos más notables de la semana
2. Luego para cada uno encuentra el dato más específico
3. Finalmente formula la acción concreta

Responde SOLO JSON (sin markdown, sin texto adicional):
{ "resumen_ejecutivo": "2-3 oraciones",
  "hallazgo_1": "como el ejemplo",
  "hallazgo_2": "...",
  "hallazgo_3": "...",
  "riesgo_1": "...",
  "oportunidad_1": "...",
  "accion_1": "...",
  "accion_2": "..." }
```

### 1.3 Ejecuta y compara antes/después

1. Reemplaza el prompt en el módulo HTTP del Escenario 2
2. Run once
3. Toma screenshot del PDF nuevo
4. Compará con el PDF de Clase 5

Documenta en tu tabla de parámetros:

| Marcador | Antes (C05) | Después (C06) |
|----------|-------------|---------------|
| hallazgo_1 | "Juan vendió bien" | "Juan generó 45% de ventas (+22% vs promedio)..." |

✅ **Checkpoint:** Al menos 3 marcadores tipo IA muestran diferencia notable antes/después. Diferencia documentada en la tabla de parámetros.

---

## Actividad 2: Aplica las 4 mejores prácticas (40 min)

### 2.1 Nombre de archivo con fecha dinámica

En el módulo **Export as PDF** del Escenario 2, edita el nombre del archivo:

```
Reporte_{{formatDate(now; "YYYY-MM-DD")}}.pdf
```

Resultado: `Reporte_2026-04-19.pdf`. Los PDFs quedan ordenados cronológicamente.

### 2.2 Carpeta Backups en Drive

1. Crea carpeta `Backups` dentro de "Proyecto de Instrucción"
2. Después del Export as PDF, agrega módulo **Google Drive → Upload a file**
   - **Folder:** Backups
   - **File:** el PDF del módulo anterior
   - **File name:** mismo nombre con fecha

### 2.3 Error handler con alerta

1. Click derecho en el módulo más frágil (HTTP a Gemini) → **Add error handler → Resume**
2. En el handler, agrega **Gmail → Send an Email**:
   - **Subject:** `❌ Error en flujo del reporte — {{now}}`
   - **Content:** `El módulo [nombre] falló. Revisar Make History en el escenario [link].`
   - **To:** tu correo

### 2.4 Pestaña Logs en Sheet

1. En tu Sheet, crea nueva pestaña `Logs` con columnas: `Fecha`, `Hora`, `Escenario`, `Estado`, `Duracion`, `Error`
2. Al inicio del Escenario 2, agrega **Tools → Set variable** → `inicio = now`
3. Al final del Escenario 2 (después de Historico), agrega **Google Sheets → Add a row**:
   - Pestaña: `Logs`
   - Valores: fecha, hora, "Reporte Semanal", "OK", `now - inicio`, null

En el error handler del 2.3, agrega también Add a row en Logs con Estado = "Error".

✅ **Checkpoint:** Tu sistema tiene: nombre con fecha, backup en Drive, error handler con alerta, pestaña Logs alimentándose.

---

## Actividad 3: Define tu plan de personalización (30 min)

### 3.1 Revisa tu brief original de Clase 1

Abre el brief que escribiste en la Clase 1. Léelo otra vez con el sistema modelo en mente.

### 3.2 Identifica los 5 puntos críticos

Para cada uno, especifica qué cambiarás en Clase 7:

| # | Punto | Caso Roberto | TU caso |
|---|-------|--------------|---------|
| 1 | Datos de entrada | Correos de ventas | [<!-- tus correos, forms, chats -->] |
| 2 | Estructura del Sheet | Columnas de ventas | [<!-- tus columnas propias -->] |
| 3 | Plantilla de Slides | Marca genérica | [<!-- tu logo, colores, tipografía -->] |
| 4 | Prompts de Gemini | Caso ventas | [<!-- tu contexto profesional -->] |
| 5 | Destinatarios y frecuencia | Gerente, semanal | [<!-- tu destinatario, tu frecuencia -->] |

### 3.3 Actualiza tabla de parámetros para tu caso

Duplica la sección "Marcadores" de la tabla de parámetros. Crea una versión "Tu Caso" donde adaptas nombres:

| Marcador genérico | Tu versión |
|-------------------|------------|
| `{{ventas_total}}` | `{{horas_facturadas}}` (para consultores) |
| `{{clientes_nuevos}}` | `{{leads_calificados}}` (para marketing) |

### 3.4 Preview del proyecto de Clase 7

Escribe en 2-3 líneas en tu brief actualizado:

```
En Clase 7 voy a adaptar el sistema para:
- [Describí tu caso con más detalle que en C1]
- [Qué va a ser lo más difícil de personalizar]
- [Qué datos reales vas a usar]
```

✅ **Checkpoint:** Plan de personalización con 5 puntos concretos, tabla de parámetros actualizada y preview del proyecto escrito.

---

## 📁 Estructura Final del Proyecto

```
Make.com/
├── Escenario 1: Gmail → Gemini → Sheet (Instant, activo con prompt optimizado)
└── Escenario 2: Sheet → Gemini → Slides → PDF → Gmail + Backup + Historico + Log
    └── Error handler con alerta por correo

Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc (actualizado con preview de Clase 7)
    ├── Tabla-de-Parámetros.doc (con secciones: Antes/Después + Plan Personalización)
    ├── sistema-reporte.xlsx (con pestaña Logs nueva)
    ├── Reporte-Plantilla.slides
    └── Backups/ (PDFs de cada corrida)
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Cuál de las 3 técnicas de prompt engineering (persona, few-shot, chain-of-thought) sentiste que cambió más la calidad?**
2. **¿Cuál de las 4 mejores prácticas vas a extender a otros sistemas de tu trabajo?**
3. **¿Cuál de los 5 puntos de personalización va a ser el más difícil en Clase 7?**

---

## Logros Adicionales (Opcional)

### 🟢 Agrega un segundo prompt para el flujo instantáneo
El prompt de extracción de correos también puede mejorarse con few-shot. Agrega 2 ejemplos de correo → JSON esperado.

### 🟡 Dashboard de Logs
Crea un gráfico en la pestaña Logs que muestre éxitos/errores por semana. Útil para ver salud del sistema.

### 🔴 Prueba el modelo gemini-2.0-flash-thinking
Cambia el modelo en el HTTP. Este modelo "piensa" más antes de responder — compara calidad con el flash estándar.

---

## 📝 Entrega

### Checklist

- [ ] 3 prompts optimizados con antes/después documentado en tabla de parámetros
- [ ] 4 mejores prácticas aplicadas y verificadas
- [ ] Plan de personalización con 5 puntos críticos
- [ ] Tabla de parámetros actualizada con "Tu versión" de marcadores

### Entregable

📸 **Screenshots** mostrando:
- Dos PDFs lado a lado: versión Clase 5 (prompt plano) vs versión Clase 6 (prompt optimizado)
- Pestaña `Logs` del Sheet con al menos 2 entradas
- Error handler configurado en el Escenario 2
- Sección "Plan de Personalización" de la tabla de parámetros

> ⚠️ Los screenshots deben mostrar tu cuenta de Google visible.
