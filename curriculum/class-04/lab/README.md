# Lab 04: Make básico — Tus primeros 2 flujos sin IA

> ⚠️ **Lab Calificado** - Este lab será evaluado según la rúbrica incluida abajo.
>
> 📌 **Distribución:** Se espera completar ~50% durante la sesión en vivo (Actividades 1-2) y el resto antes de la fecha de entrega.

## 🎯 Objetivos del Módulo

Este lab integra todo lo aprendido en el Módulo 1:

1. Construir el flujo Gmail → Sheet con Instant Trigger funcionando end-to-end.
2. Construir el flujo Sheet → Slides → PDF → Gmail con ≥5 marcadores reemplazados.
3. Aplicar mejoras básicas (nombre de PDF con fecha, error handler).

---

## 🔑 Conceptos Clave

- **Escenario de Make** — flujo visual sin código que conecta módulos con un trigger.
- **Instant Trigger** — activación en 2-5 segundos; úsalo para efecto WOW.
- **Replace Text en Slides** — reemplaza `{{marcador}}` por un valor; 1 operación por marcador.

---

## ⚙️ Setup Inicial

Este lab integra todo el Módulo 1. Verifica que tengas todo listo:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Cuenta de Make activa | Puedes entrar a [make.com](https://make.com/){:target="_blank"} y ver tu dashboard |
| ☐ | Sheet con 3 pestañas (Clase 2) | `VentasSemanaActual`, `Config`, `Historico` funcionando |
| ☐ | Plantilla de Slides (Clase 3) | 6 slides con ~18-20 marcadores insertados |
| ☐ | Tabla de parámetros actualizada | Marcadores documentados con tipo y origen |

> ⚠️ Si te falta alguno, completa primero. Make necesita el Sheet y la plantilla con marcadores para poder conectarlos.

---

## Actividad 1: Gmail → Sheet con Instant Trigger (40 min)

### 1.1 Crea el primer escenario

En Make → **+ Create a new scenario**. Nómbralo:

```
Captura: Correo → [<!-- Tu proyecto -->]
```

### 1.2 Agrega el módulo Gmail Watch Emails (Instant)

Busca **Gmail → Watch Emails**. Elige el modo **Instant**.

- **Folder:** Inbox
- **Filter by subject contains:** `Ventas del día` (o el asunto que defines para tu caso)
- **Mark message as:** Read (opcional)

Conecta tu cuenta de Gmail cuando pida permisos.

### 1.3 Agrega Google Sheets Add a Row

Después de Gmail, **+ Add module → Google Sheets → Add a row**.

- **Spreadsheet:** tu Sheet del sistema
- **Sheet:** `VentasSemanaActual`
- **Values:** mapea las columnas a campos del correo:
  - `Fecha` → `{{1.date}}` (fecha del correo)
  - `Descripción` → `{{1.text}}` (cuerpo del correo)
  - Los demás campos quedan vacíos por ahora — los llenará Gemini en Clase 5

### 1.4 Prueba en vivo

1. Guarda el escenario y activa el toggle "On"
2. Envíate 3 correos con el asunto exacto (ej: "Ventas del día - Lunes")
3. Ve tu Sheet — deberías ver 3 filas nuevas en segundos

✅ **Checkpoint:** Al enviar un correo con el asunto filtro, el Sheet agrega una fila nueva en <10 segundos.

---

## Actividad 2: Sheet → Slides → PDF → Gmail (35 min)

### 2.1 Crea el segundo escenario

**+ Create a new scenario**. Nómbralo:

```
Reporte: [<!-- Tu proyecto -->] Semanal
```

Este escenario lo vas a correr manualmente por ahora (Run once). En Clase 5 lo convertirás en Scheduled.

### 2.2 Agrega Google Sheets Search Rows

**Google Sheets → Search Rows**.

- **Spreadsheet:** tu Sheet
- **Sheet:** `VentasSemanaActual`
- **Filter:** las filas de la última semana (o deja vacío por ahora para traer todo)

### 2.3 Agrega Google Slides Create a Presentation from a Template

**Google Slides → Create a Presentation from a Template**.

- **Template:** tu plantilla de la Clase 3
- **Destination folder:** la carpeta "Proyecto de Instrucción" en Drive

### 2.4 Agrega Replace Text (uno por cada marcador crudo/calculado)

Por cada marcador crudo o calculado que quieras llenar, agrega **Google Slides → Replace Text**:

- **Presentation:** output del paso anterior
- **Old text:** `{{ventas_total}}` (sin espacios, exacto como está en la plantilla)
- **New text:** fórmula o valor a mapear

**Para marcadores calculados (tipo 2):** agrega primero un módulo **Math** o **Date** para calcular el valor.

Ejemplos de calculados:
- `{{semana}}` → módulo **Date** → `formatDate(now; "DD/MM")` + " - " + fecha fin semana
- `{{variacion_pct}}` → módulo **Math** → `(ventas_actual - ventas_anterior) / ventas_anterior * 100`
- `{{meta_cumplida_pct}}` → **Math** → `ventas_total / meta_config * 100`

**Meta:** al menos 5 marcadores (tipo 1 y 2) reemplazados. Los tipo 3 (IA) quedan vacíos — los llenamos en Clase 5.

✅ **Checkpoint:** Al correr el escenario (Run once), la plantilla duplicada tiene valores reales en ≥5 marcadores.

---

## Actividad 3: Exporta PDF y envía por Gmail (25 min)

### 3.1 Agrega Google Slides Export as PDF

**Google Slides → Export a Presentation**.

- **Presentation:** output del último Replace Text
- **Format:** PDF

### 3.2 Agrega Gmail Send an Email

**Gmail → Send an Email**.

- **To:** tu correo
- **Subject:** `Reporte semanal - [<!-- proyecto -->]`
- **Content:** texto corto anunciando el reporte
- **Attachments:** el PDF del paso anterior

### 3.3 Run once del flujo completo

Ejecuta el escenario con el botón **Run once**. Observa cada módulo ejecutar.

### 3.4 Verifica el correo

Abre tu bandeja de entrada — debe llegar un correo con el PDF adjunto con los marcadores reemplazados.

✅ **Checkpoint:** El PDF en tu bandeja muestra los marcadores crudos y calculados reemplazados por valores reales.

---

## Actividad 4: Desafío Avanzado (post-clase, 30-45 min)

> 🔥 **Desafío Post-Clase** - Esta sección se completa después de la sesión en vivo.

### 4.1 Nombre de PDF con fecha dinámica

En el módulo **Export as PDF**, edita el campo **File name** para que use la fecha:

```
Reporte_{{formatDate(now; "YYYY-MM-DD")}}.pdf
```

Resultado: `Reporte_2026-04-19.pdf`. Ordena cronológicamente en Drive automáticamente.

### 4.2 Agrega un Error Handler básico

Click derecho en el módulo más frágil (generalmente Replace Text) → **Add error handler → Resume**.

En el handler, agrega un módulo **Gmail → Send an Email** a tu correo con:
- **Subject:** `❌ Error en flujo del reporte`
- **Content:** `El flujo falló en el módulo [nombre]. Revisar Make History.`

✅ **Checkpoint:** El escenario tiene nombre de PDF con fecha y al menos 1 error handler configurado.

### 4.3 Sube el escenario a una carpeta de Backups

En Drive, crea carpeta `Backups` y configura que Make guarde una copia del PDF ahí también (segundo módulo Gmail → Copy to folder).

---

## 📁 Estructura Final del Proyecto

```
Make.com/
├── Escenario 1: Captura Correo → Sheet (Instant, activo)
└── Escenario 2: Reporte Semanal (Manual, Run once)

Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc
    ├── Tabla-de-Parámetros.doc
    ├── sistema-reporte.xlsx  (Sheet, ahora recibe filas de correos)
    ├── Reporte-Plantilla.slides
    └── Backups/
        └── Reporte_2026-04-19.pdf  (si completaste el desafío)
```

---

## Verificación Final

Usa la rúbrica de abajo para verificar que tu proyecto esté completo antes de entregar.

---

## Reflexión

Responde en tu documento:

1. **¿Qué habilidad del Módulo 1 te parece más valiosa para tu trabajo inmediato?**
2. **¿Qué cambiarías en tu forma de trabajar a partir de hoy?**
3. **¿Qué te entusiasma más del Módulo 2 cuando integremos IA en estos flujos?**

---

## Logros Adicionales (Opcional)

### 🟢 Agrega logs en una pestaña del Sheet
Crea una pestaña `Logs` y haz que cada ejecución del escenario 2 registre fecha, hora y resultado (éxito/error). Preview de mejores prácticas de Clase 6.

### 🟡 Configura filtro de asunto con regex
En lugar de "contains", usa expresión regular para capturar varios formatos: `^(Ventas del día|Vtas|Reporte).*`. Más flexibilidad al vendedor.

### 🔴 Prepara el scheduled trigger
Duplica el Escenario 2 y cámbiale el trigger a **Scheduled** cada viernes 4pm. Todavía no lo actives — lo completas en la Clase 5 cuando agreguemos IA.

---

## Rúbrica de Evaluación

| Criterio | Excelente (20) | Bueno (15) | Satisfactorio (10) | Bajo (5) |
|----------|---------------|------------|-------------------|----------|
| **Escenario 1 — Gmail → Sheet** | Instant Trigger activo, filtro correcto, 3+ filas registradas en prueba | Funciona pero sin filtro específico | Funciona manual, no Instant | No funciona end-to-end |
| **Escenario 2 — Flujo del reporte** | ≥8 marcadores reemplazados (crudos y calculados), PDF generado | 5-7 marcadores reemplazados | 3-4 marcadores reemplazados | <3 marcadores o PDF no se genera |
| **Entrega por Gmail** | Correo llega con PDF adjunto, asunto descriptivo | PDF llega pero asunto genérico | PDF generado pero no enviado | No llega correo |
| **Mejores prácticas (desafío)** | Nombre con fecha + error handler + backup folder | Nombre con fecha + error handler | Solo nombre con fecha | Sin mejoras aplicadas |
| **Tabla de parámetros actualizada** | Documentados todos los mapeos de Make (módulos, operaciones, conexiones) | Mapeos principales documentados | Solo estructura básica registrada | Sin actualización post-lab |

**Total: 100 puntos** (5 criterios x 20 pts)

| Nota | Rango |
|------|-------|
| A | 90-100 |
| B | 80-89 |
| C | 70-79 |
| F | < 70 |

---

## 📝 Entrega

📦 **Entregable:**

1. **Screenshots** del proyecto terminado mostrando:
   - **Escenario 1** activo en Make (toggle "On" visible)
   - **Sheet** con al menos 3 filas agregadas por el Instant Trigger (con hora registrada)
   - **Escenario 2** completo en Make (vista del flujo completo con todos los módulos)
   - **PDF generado** llegando al correo con marcadores reemplazados
   - Tu nombre o correo visible en al menos 2 de los 4 screenshots

2. **Fuente:** link compartido (con permisos de lectura) a la carpeta "Proyecto de Instrucción" en Drive.
