<!-- .slide: data-background="#0A192F" -->

# SESIÓN 5
## PLANTILLAS CON PLACEHOLDERS

Genera documentos con formato profesional automáticamente

*Sesión 5 de 8 · 60 minutos · Online en vivo*

---

## TRANSICIÓN · DE DATOS A DOCUMENTOS

### La sesión pasada:

- La IA devolvió datos estructurados (JSON)
- Cada campo cayó en su columna del Sheet

### Hoy:

- Convertimos esos datos en **documentos con formato**
- Una plantilla que se llena sola

> "Hoy tus datos se vuelven un reporte presentable."

---

## QUÉ VAMOS A LOGRAR HOY

### OBJETIVO DE LA SESIÓN

Generar documentos y presentaciones automáticas usando plantillas con placeholders `{{variable}}` en Docs/Slides.

### FUNDAMENTOS

1. ¿Qué es una plantilla?
2. Placeholders `{{variable}}`
3. Mapeo dato → placeholder
4. Plantillas en Slides y Docs
5. Formato de datos (fechas, números, monedas)

### MINI-PROYECTO

Reporte mensual de facturas

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿Cuántos reportes haces al mes que son el mismo formato?

**02** ¿Tienes alguna plantilla en Word/Slides que repites?

**03** ¿Cuánto tiempo te toma armar uno a mano?

> 💡 Las plantillas con placeholders convierten ese tiempo manual en cero.

---

## FUNDAMENTO 1 · ¿QUÉ ES UNA PLANTILLA?

*Un esqueleto reutilizable*

- El **formato y diseño** están fijos
- Los **datos** cambian cada vez

> Pensá en una factura o un contrato: el formato es siempre el mismo, solo cambia el contenido.

---

## FUNDAMENTO 2 · PLACEHOLDERS {{variable}}

*Marcadores que Make reemplaza por datos reales*

- En Docs/Slides escribís: `Hola {{nombre}}, tu total es {{monto}}`
- Make reemplaza `{{nombre}}` → "Ana", `{{monto}}` → "S/ 1,500"
- Tipos: texto, número, fecha, link de imagen
- ⚠️ Los nombres deben **coincidir exactamente** con tus variables

---

## EJEMPLO REAL · PLANTILLA DE SLIDES

*Lo que escribís y lo que aparece después*

```
┌────────────────────────────────────┐
│  REPORTE MENSUAL DE FACTURAS        │
│  {{mes}} {{anio}}                   │
│                                     │
│  Total facturado:  {{total}}        │
│  Top proveedor:    {{top_proveedor}}│
│  Generado el {{fecha_generacion}}   │
└────────────────────────────────────┘
```

---

## FUNDAMENTO 3 · MAPEO DATO → PLACEHOLDER

*El paso clave: qué variable va en cada marcador*

- **DATO** — fila del Sheet
- **MAPEO** — variable → `{{placeholder}}`
- **DOC FINAL** — ya con los datos

> Si el nombre no coincide, el marcador queda sin reemplazar.

---

## FUNDAMENTO 4 · PLANTILLAS EN SLIDES Y DOCS

*Make tiene módulos específicos: Create from Template*

| GOOGLE DOCS | GOOGLE SLIDES |
|-------------|---------------|
| Ficha de cliente | Reporte ejecutivo |
| Carta de respuesta | Dashboard visual |
| Reporte narrativo | Presentación |

---

## FUNDAMENTO 5 · FORMATO DE DATOS

*Antes de inyectar al placeholder, convertir el formato*

- Fechas: `2026-06-01` → `1 de junio de 2026` (formatDate)
- Números: `1500` → `S/ 1,500.00` (formatNumber)
- Mayúsculas/minúsculas según la plantilla

> Make tiene funciones built-in para todas estas transformaciones.

---

## MINI-PROYECTO · REPORTE MENSUAL DE FACTURAS

*Sheet → Slide con plantilla → Drive/email*

**Individual**

### QUÉ HACER

1. Diseñar la plantilla en Slides con placeholders `{{mes}}`, `{{total}}`, `{{top_proveedor}}`...
2. Crear escenario que lea el Sheet de facturas (**Search Rows**)
3. Calcular agregados (total, top proveedor, ranking)
4. Módulo **Create a Presentation from Template** + mapear cada placeholder
5. Probar y revisar el Slide generado

✓ **Verificación:** Slide del reporte con datos reales y formato profesional

---

## LO QUE TE LLEVAS HOY

**01** Plantilla en Slides con placeholders funcionando

**02** Escenario que genera el reporte automáticamente

**03** Saber convertir formatos de fecha, número y moneda

### PRÓXIMA SESIÓN

Sesión 6: Armamos el flujo completo de inicio a fin, robusto, con filtros y manejo de errores.
