# Plantillas — AI 101

Plantillas listas para usar durante el curso (caso guía: sistema de facturas).

---

## Índice

1. [Sheet de registro de facturas (Sesión 02)](#1-sheet-de-registro-de-facturas-sesión-02)
2. [Sheet de ventas estructurado (Sesión 04)](#2-sheet-de-ventas-estructurado-sesión-04)
3. [Data Structure — el molde del JSON (Sesión 04)](#3-data-structure--el-molde-del-json-sesión-04)
4. [Plantilla de Slides con placeholders (Sesión 05)](#4-plantilla-de-slides-con-placeholders-sesión-05)
5. [Escenarios de Make (resumen)](#5-escenarios-de-make-resumen)
6. [Roadmap personal (Sesión 08)](#6-roadmap-personal-sesión-08)

---

## 1. Sheet de registro de facturas (Sesión 02)

Hoja `Facturas-Registro`:

| Nombre archivo | Fecha de subida | Link | Proveedor |
|----------------|-----------------|------|-----------|
| factura-001.pdf | YYYY-MM-DD | https://... | (se llena con IA en S03) |

---

## 2. Sheet de ventas estructurado (Sesión 04)

Hoja `Ventas` (alimentada por Gemini + Parse JSON desde Gmail):

| vendedor | cliente | producto | monto | fecha |
|----------|---------|----------|-------|-------|
| Ana | Acme S.A. | Consultoría | 1500 | 2026-06-01 |

---

## 3. Data Structure — el molde del JSON (Sesión 04)

Lo que defines en Make para que Parse JSON genere variables:

| Campo | Tipo | Requerido |
|-------|------|-----------|
| vendedor | Text | Sí |
| cliente | Text | Sí |
| producto | Text | Sí |
| monto | Number | Sí |
| fecha | Date (ISO) | Sí |
| tipo | Text | Opcional |

System prompt que produce ese JSON:

```
Devuelve SOLO un JSON con estos campos, sin texto adicional:
{ "vendedor": "", "cliente": "", "producto": "", "monto": 0, "fecha": "YYYY-MM-DD" }
```

---

## 4. Plantilla de Slides con placeholders (Sesión 05)

Diseña la plantilla con marcadores `{{variable}}`; Make los reemplaza con datos reales.

### Reporte mensual de facturas

```
REPORTE MENSUAL DE FACTURAS
{{mes}} {{anio}}

Total facturado:   {{total}}
Top proveedor:     {{top_proveedor}}
N° de facturas:    {{num_facturas}}

Generado el {{fecha_generacion}}
```

> Regla: el nombre del placeholder debe coincidir **exacto** con el del mapeo en Make (sin espacios ni mayúsculas distintas).

### Formato de datos (antes de inyectar)

```
{{total}}            → "S/ " + formatNumber(total; 2)
{{mes}}              → formatDate(now; "MMMM")
{{fecha_generacion}} → formatDate(now; "D [de] MMMM [de] YYYY")
```

---

## 5. Escenarios de Make (resumen)

El sistema de facturas se arma en estos escenarios (se duplican y adaptan para el proyecto propio en S07):

| Escenario | Trigger | Flujo |
|-----------|---------|-------|
| Registro de facturas | Drive Watch Files | Drive → Gemini (proveedor) → Sheet |
| Ventas desde Gmail | Gmail Watch Emails | Gmail → Gemini (JSON) → Parse JSON → Sheet |
| Reporte mensual | Schedule / Run once | Sheet (Search Rows) → Create from Template → Drive/Email |
| Flujo robusto | Watch + Schedule | Drive → IA → Sheets → Docs → Email + filtros + router + error handler |

---

## 6. Roadmap personal (Sesión 08)

Cierre del curso: define tu próxima automatización.

```
Mi próxima automatización será [proceso de tu trabajo].
Los datos salen de [origen] y van a [destino].
La construiré en las próximas [semanas].
```
