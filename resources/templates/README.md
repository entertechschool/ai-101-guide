# Plantillas — AI 101

Plantillas listas para usar durante el curso.

---

## Índice

1. [Brief del proyecto de instrucción](#1-brief-del-proyecto-de-instruccion)
2. [Estructura del Sheet (3 pestañas)](#2-estructura-del-sheet-3-pestañas)
3. [Tabla de parámetros](#3-tabla-de-parametros)
4. [Plantilla de Slides (6 secciones)](#4-plantilla-de-slides-6-secciones)
5. [Cálculo de ROI](#5-calculo-de-roi)
6. [Plan 30 días](#6-plan-30-dias)

---

## 1. Brief del proyecto de instrucción

Plantilla para el Google Doc de la Clase 01:

```
Quiero automatizar [tipo de reporte] que genero [frecuencia],
dirigido a [destinatario],
que incluye [tipo de datos],
para ahorrar [tiempo estimado].
```

**Ejemplo completo:**

> "Quiero automatizar el reporte semanal de ventas que genero cada viernes, dirigido a mis 3 vendedores y al gerente general, que incluye ventas totales, clientes nuevos y hallazgos por vendedor, para ahorrar 4 horas semanales."

---

## 2. Estructura del Sheet (3 pestañas)

### Pestaña 1: Operativa (ejemplo `VentasSemanaActual`)

| Fecha | Vendedor | Cliente | Producto | Monto | Tipo | Descripción |
|-------|----------|---------|----------|-------|------|-------------|
| YYYY-MM-DD | Nombre | Empresa | Servicio | 1000 | Nuevo/Recurrente | Texto contexto 1 línea |

### Pestaña 2: Config

| Parámetro | Valor |
|-----------|-------|
| Meta semanal | S/ 20,000 |
| Ticket promedio objetivo | S/ 2,800 |
| Vendedores del equipo | Juan, María, Carlos |
| Meta por vendedor | S/ 5,000 |
| % objetivo clientes nuevos | 30 |

### Pestaña 3: Historico

| Semana | Ventas_Total | Clientes_Nuevos | Ticket_Promedio | Meta_Cumplida_Pct |
|--------|-------------|-----------------|-----------------|-------------------|
| 01-07 abril | 18500 | 6 | 2642 | 92 |

### Rangos nombrados (Datos → Rangos con nombre)

```
RangoVentas    →  VentasSemanaActual!A:G
RangoConfig    →  Config!A:B
RangoHistorico →  Historico!A:E
```

---

## 3. Tabla de parámetros

Documento vivo del curso. Se crea en Clase 02 y crece durante las 8 sesiones.

### Sección: Sheet

| Categoría | Item | Valor |
|-----------|------|-------|
| Pestaña operativa | Nombre | `VentasSemanaActual` |
| Pestaña operativa | Columnas | Fecha, Vendedor, Cliente, Producto, Monto, Tipo, Descripción |
| Pestaña config | Nombre | `Config` |
| Pestaña config | Parámetros | Meta semanal, Ticket objetivo, Vendedores, Meta/vendedor |
| Pestaña histórica | Nombre | `Historico` |
| Pestaña histórica | Columnas | Semana, Ventas_Total, Clientes_Nuevos, Ticket_Promedio, Meta_Cumplida_Pct |
| Rango nombrado | `RangoVentas` | `VentasSemanaActual!A:G` |
| Rango nombrado | `RangoConfig` | `Config!A:B` |
| Rango nombrado | `RangoHistorico` | `Historico!A:E` |

### Sección: Marcadores de Slides

| Marcador | Tipo | Origen | Ejemplo |
|----------|------|--------|---------|
| `{{semana}}` | Calculado | Make (fechas) | "13-19 abril" |
| `{{ventas_total}}` | Crudo | Sheet | "21,700" |
| `{{variacion_pct}}` | Calculado | Make | "+12%" |
| `{{clientes_nuevos}}` | Crudo | Sheet | "8" |
| `{{meta_cumplida_pct}}` | Calculado | Make | "108%" |
| `{{resumen_ejecutivo}}` | IA | Gemini | Párrafo |
| `{{hallazgo_1}}` | IA | Gemini | Texto |
| `{{hallazgo_2}}` | IA | Gemini | Texto |
| `{{hallazgo_3}}` | IA | Gemini | Texto |
| `{{riesgo_1}}` | IA | Gemini | Texto |
| `{{riesgo_2}}` | IA | Gemini | Texto |
| `{{oportunidad_1}}` | IA | Gemini | Texto |
| `{{grafico_ventas}}` | Crudo | Sheet (imagen) | — |
| `{{accion_1}}` | IA | Gemini | Texto |
| `{{accion_2}}` | IA | Gemini | Texto |
| `{{fecha_reporte}}` | Calculado | Make | "19-04-2026" |

### Sección: Make

| Categoría | Item | Valor |
|-----------|------|-------|
| Escenario 1 | Nombre | `Captura: Correo → [caso]` |
| Escenario 1 | Trigger | Gmail Watch Emails (Instant) |
| Escenario 1 | Filtro | `subject contains "Ventas del día"` |
| Escenario 2 | Nombre | `Reporte: [caso] Semanal` |
| Escenario 2 | Trigger | Scheduled Viernes 4pm |
| Error handler | Módulo | HTTP Gemini |
| Logs | Pestaña | `Logs` (en Sheet) |

---

## 4. Plantilla de Slides (6 secciones)

### Slide 1: Portada

```
{{empresa_nombre}}
Reporte Ejecutivo — {{semana}}
Fecha: {{fecha_reporte}}
```

### Slide 2: Resumen Ejecutivo

```
Esta semana: {{ventas_total}} ({{variacion_pct}} vs anterior)

{{resumen_ejecutivo}}

Clientes nuevos: {{clientes_nuevos}}
Meta cumplida: {{meta_cumplida_pct}}%
```

### Slide 3: Hallazgos

```
1. {{hallazgo_1}}
2. {{hallazgo_2}}
3. {{hallazgo_3}}
```

### Slide 4: Visualización

```
[Gráfico vinculado al Sheet — pestaña VentasSemanaActual]
```

### Slide 5: Riesgos y Oportunidades

```
RIESGOS:
• {{riesgo_1}}
• {{riesgo_2}}

OPORTUNIDADES:
• {{oportunidad_1}}
```

### Slide 6: Próximos Pasos

```
1. {{accion_1}}
2. {{accion_2}}

Próximo reporte: {{proximo_reporte}}
```

---

## 5. Cálculo de ROI

Fórmula (Clase 08):

```
Ahorro MENSUAL = Horas ahorradas/semana × Tarifa/hora × 4 semanas
Ahorro ANUAL = Ahorro mensual × 12
```

### Ejemplo (caso Roberto)

| Concepto | Valor |
|----------|-------|
| Horas ahorradas/semana | 6 |
| Tarifa por hora | S/ 100 |
| Ahorro mensual | S/ 2,400 |
| Ahorro anual | S/ 28,800 |

### Frase de 1 línea para comunicar

```
"Construí un sistema automatizado que me ahorra [X] horas al mes,
equivalente a S/ [Y] al año, usando IA gratuita."
```

### Si no sabés tu tarifa (asalariado)

```
Tarifa efectiva = Salario mensual neto ÷ Horas trabajadas al mes

Ejemplo:
- Salario: S/ 4,000/mes
- Horas/mes: 160 (8h × 20 días)
- Tarifa efectiva: S/ 25/hora
```

---

## 6. Plan 30 días

Plantilla (Clase 08):

### Paso 1: Lista de 10 tareas repetitivas

```
1. [Tarea]
2. [Tarea]
3. [Tarea]
...
10. [Tarea]
```

### Paso 2: Aplicar 80/20

Marcá con ⭐ las 3 que concentran 80% del tiempo.

### Paso 3: Diseño de 3 agentes

| Agente | Qué automatiza | Datos que necesita | Herramientas | Semana |
|--------|----------------|--------------------|--------------|--------|
| Agente 1 | [tarea ⭐ #1] | [input] | Gemini + Make + [...] | Semana 1 |
| Agente 2 | [tarea ⭐ #2] | [input] | [...] | Semana 2 |
| Agente 3 | [tarea ⭐ #3] | [input] | [...] | Semana 3 |
| Ajustes | Medición ROI agregado | — | — | Semana 4 |

### Paso 4: Compromiso público

```
"En los próximos 30 días voy a construir:
Semana 1: [Agente 1]
Semana 2: [Agente 2]
Semana 3: [Agente 3]
Semana 4: ajustes y medición de ROI agregado."
```
