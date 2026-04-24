# Lab 07: Tu proyecto propio

## 🎯 Objetivos

1. Construir un Sheet personalizado con 3 pestañas adaptado a tu caso real, con datos reales.
2. Adaptar la plantilla de Slides con tu marca + duplicar los 2 escenarios de Make con prompts propios.
3. Validar el sistema propio end-to-end con 3 correos de prueba reales.

---

## 🔑 Conceptos Clave

- **Transferencia del patrón** — la arquitectura se queda, el cerebro cambia.
- **Clonación de escenarios** — duplicar flujos completos en Make vía Export/Import Blueprint.
- **Validación con datos reales** — enviar correos/formularios reales, no simulados de tutorial.

---

## ⚙️ Setup Inicial

Este lab asume que el sistema modelo está funcionando y optimizado:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Sistema modelo C06 funcionando | Los 2 escenarios activos con prompts optimizados |
| ☐ | Plan personalización con 5 puntos | De Clase 6, en la tabla de parámetros |
| ☐ | Datos reales listos | Al menos 5 registros verídicos de tu trabajo |
| ☐ | Elementos de marca | Logo + paleta + tipografía |

> 💡 **Acompañamiento 1 a 1:** El instructor circulará entre estudiantes durante todo el lab. Pide ayuda cuando la necesites.

---

## Actividad 1: Construye tu Sheet personalizado (50 min)

### 1.1 Duplica el Sheet modelo

En tu Sheet modelo → **Archivo → Hacer una copia**. Nombra la copia:

```
Sistema [<!-- tu proyecto -->] — v2 (mi caso real)
```

### 1.2 Renombra las 3 pestañas

| Pestaña modelo | Tu pestaña |
|----------------|-----------|
| `VentasSemanaActual` | `[<!-- EntidadSemanaActual -->]` |
| `Config` | `Config` (igual) |
| `Historico` | `Historico` (igual) |

**Ejemplos según industria:**
- Marketing: `CampanasSemanaActual`
- Consultoría: `HorasSemanaActual` o `ProyectosSemanaActual`
- Ecommerce: `PedidosSemanaActual`
- Academia: `CohortesSemana` o `EntregasSemana`

### 1.3 Renombra columnas de la pestaña operativa

Según el ejemplo de tu industria:

| Caso Roberto (original) | Marketing | Consultoría |
|-------------------------|-----------|-------------|
| Fecha | Fecha | Fecha |
| Vendedor | Especialista | Consultor |
| Cliente | Campaña | Cliente/Proyecto |
| Producto | Canal | Tipo de servicio |
| Monto | Alcance | Horas |
| Tipo (Nuevo/Recurrente) | Orgánico/Pagado | Fijo/Variable |
| Descripción | Descripción | Descripción |

### 1.4 Adapta la pestaña Config con parámetros reales

Reemplaza los valores del caso Roberto con TUS valores:
- Tu meta real
- Tu equipo real (nombres)
- Tus categorías o servicios
- Tu ticket objetivo (o métrica equivalente)

### 1.5 Llena Historico con 2-3 semanas reales

Si tenés datos históricos, pégalos. Si no, inventa datos realistas para tener base de comparación en los insights de Gemini.

### 1.6 Actualiza rangos nombrados

Tus rangos ahora apuntan a las pestañas renombradas. Ve a **Datos → Rangos con nombre** y actualiza:
- `RangoVentas` → puede renombrarse a `RangoOperacional` (y apuntar a tu pestaña `[Entidad]SemanaActual`)
- `RangoConfig` → igual
- `RangoHistorico` → igual

> ⚠️ Si renombras los rangos, recordá actualizar Make en la Actividad 2.

✅ **Checkpoint:** Tu Sheet tiene 3 pestañas con nombres de tu caso, columnas propias, datos reales y rangos nombrados actualizados.

---

## Actividad 2: Adapta Slides + duplica flujos (50 min)

### 2.1 Duplica la plantilla de Slides

En tu plantilla modelo → **Archivo → Hacer una copia**. Nombre:

```
Reporte [<!-- tu proyecto -->] — Plantilla v2
```

### 2.2 Aplica tu marca

- **Logo:** insertalo en la Portada (esquina superior izquierda o derecha)
- **Colores:** cambia el fondo y acentos a tu paleta hex
- **Tipografía:** cambia las fuentes a las de tu marca (o similares en Google Fonts)

### 2.3 Renombra marcadores según tu caso

Los marcadores del modelo se mantienen en snake_case, pero con nombres de tu dominio:

| Caso Roberto | Marketing | Consultoría |
|--------------|-----------|-------------|
| `{{ventas_total}}` | `{{alcance_total}}` | `{{horas_facturadas}}` |
| `{{clientes_nuevos}}` | `{{leads_generados}}` | `{{proyectos_activos}}` |
| `{{hallazgo_1}}` | `{{hallazgo_1}}` (mantener) | `{{hallazgo_1}}` (mantener) |

Reemplaza los nombres de los marcadores crudos/calculados; los de IA pueden quedar igual (el contenido se adapta con el prompt).

### 2.4 Duplica los 2 escenarios de Make

**Opción A (rápida):**
1. Abre el Escenario 1 modelo en Make
2. **Menú (...)**: → **Export Blueprint** → descarga JSON
3. **+ Create scenario** → **Import Blueprint** → sube el JSON
4. Renombra: `Captura: [tu caso] v2`
5. Repite con el Escenario 2

**Opción B (manual):**
1. **Duplicar escenario** desde el menú (...) del escenario modelo

### 2.5 Reconfigura las conexiones

Cada módulo del escenario duplicado apunta al Sheet/Slides **viejos** (del modelo). Actualízalos:
- Search Rows → tu Sheet v2
- Create from Template → tu plantilla v2
- Replace Text → marcadores renombrados
- Add a row (Historico) → tu Sheet v2

### 2.6 Reemplaza los prompts de Gemini

En el módulo HTTP del Escenario 1:
- Cambia el contexto del prompt de "ventas" a tu caso
- Ajusta el schema JSON a tus columnas

En el módulo HTTP del Escenario 2:
- Cambia la persona: "analista de [tu industria] con N años"
- Cambia el contexto: meta, benchmarks de tu negocio
- Ajusta el few-shot con un ejemplo real de tu caso

✅ **Checkpoint:** Los 2 escenarios duplicados apuntan a tu Sheet/Slides v2 y los prompts de Gemini mencionan tu caso específico.

---

## Actividad 3: Valida end-to-end con datos reales (20 min)

### 3.1 Envía 3 correos de prueba REALES

Genera 3 correos con información real de tu trabajo (o simulada realista). El filtro de Gmail del Escenario 1 debe capturarlos.

### 3.2 Verifica el Sheet

Tu pestaña operativa debe recibir 3 filas nuevas con datos bien estructurados.

### 3.3 Run once del Escenario 2

Ejecuta manualmente el escenario del reporte. Observa cada módulo ejecutar:
- Search Rows lee tu pestaña
- HTTP envía a Gemini
- Parse JSON estructura la respuesta
- Replace Text llena cada marcador
- Export PDF genera el archivo
- Gmail lo envía a tu correo

### 3.4 Revisa el PDF

Abre el PDF y verifica:
- [ ] Logo en su lugar
- [ ] Paleta de marca aplicada
- [ ] Marcadores crudos llenos con TUS datos
- [ ] Marcadores calculados con fórmulas correctas
- [ ] Marcadores tipo IA con insights específicos a tu caso
- [ ] Diseño respetado (sin desbordamientos)

### 3.5 Si algo falla, debug

Estrategia:
1. Identificá el módulo que falla (Make lo marca en rojo)
2. Click derecho → **Run this module only**
3. Revisá input/output
4. Si es prompt: prueba en AI Studio primero, ajusta, vuelve a Make

### 3.6 Activa el scheduled con TU frecuencia real

Si tu reporte no es semanal (mensual, quincenal, diario), ajusta el scheduled:
- Weekly friday 4pm → [tu frecuencia real]

✅ **Checkpoint:** Enviaste 3 correos reales, el Sheet recibió 3 filas, el PDF del escenario 2 llegó con TUS datos y TU marca.

---

## 📁 Estructura Final del Proyecto

```
Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc
    ├── Tabla-de-Parámetros.doc
    ├── sistema-reporte.xlsx (modelo, referencia)
    ├── Reporte-Plantilla.slides (modelo, referencia)
    ├── Sistema-[tu-proyecto]-v2.xlsx  ← TU SHEET
    ├── Reporte-[tu-proyecto]-v2.slides ← TU PLANTILLA
    └── Backups/

Make.com/
├── Escenario 1 modelo (Roberto, referencia)
├── Escenario 2 modelo (Roberto, referencia)
├── Escenario 1 v2: [tu caso] — Captura (ACTIVO)
└── Escenario 2 v2: [tu caso] — Reporte (Scheduled [tu frecuencia])
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué punto de los 5 de personalización fue el más difícil? ¿Por qué?**
2. **¿Qué insight generado por Gemini para TU caso te sorprendió?**
3. **¿Qué vas a mostrar en los 2 minutos de demo de la Clase 8?**

---

## Logros Adicionales (Opcional)

### 🟢 Agrega un segundo destinatario al correo
En el módulo Send Email, agrega CC con tu jefe, cliente o equipo. Hace que el sistema sea realmente útil (no solo para vos).

### 🟡 Crea un resumen para WhatsApp
Duplica la plantilla en versión vertical (formato móvil) con los 3 KPIs principales. Preview para compartir por WhatsApp.

### 🔴 Agrega un indicador de salud del sistema
En la pestaña Config del Sheet, agrega una celda "Último reporte OK" que el flujo actualiza al terminar. Si pasa X días sin actualizarse, sabés que algo falló.

---

## 📝 Entrega

### Checklist

- [ ] Sheet personalizado con 3 pestañas y datos reales
- [ ] Plantilla de Slides con marca propia
- [ ] 2 escenarios de Make adaptados con prompts propios
- [ ] PDF del reporte generado con datos reales verificado

### Entregable

📸 **Screenshots** mostrando:
- Tu Sheet v2 con pestañas renombradas y datos reales
- Tu plantilla Slides con logo, colores y tipografía propios
- Los 2 escenarios nuevos en Make (v2) activos
- El PDF generado con TUS datos reales abierto en pantalla

> ⚠️ El entregable debe mostrar tu cuenta de Google visible y tu caso específico, no el de Roberto.
