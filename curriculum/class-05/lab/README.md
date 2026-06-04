# Lab 05: Reporte mensual de facturas

## 🎯 Objetivo

Crear una **plantilla con placeholders** en Google Slides y un escenario de Make que la llena con datos reales del Sheet de facturas, generando un **reporte mensual** con formato profesional.

---

## 🔑 Conceptos Clave

- **Plantilla** — esqueleto con formato fijo y datos variables.
- **Placeholder** — marcador `{{variable}}` que Make reemplaza por un dato real.
- **Create from Template** — módulo de Make que genera el documento desde la plantilla.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Sheet de facturas con datos (Sesiones 2-4) | Tiene filas con proveedor, monto, fecha |
| ☐ | Conexión Google en Make (Slides + Sheets) | Disponible al agregar módulos |
| ☐ | Google Slides | Para diseñar la plantilla |

---

## Mini-proyecto: reporte mensual de facturas

> Vas a diseñar la plantilla y armar el escenario que la llena con los datos del mes.

### Paso 1: Diseña la plantilla en Slides

Crea una presentación `Reporte-Facturas-Plantilla` con un slide que contenga placeholders:

```
REPORTE MENSUAL DE FACTURAS
{{mes}} {{anio}}

Total facturado:   {{total}}
Top proveedor:     {{top_proveedor}}
N° de facturas:    {{num_facturas}}

Generado el {{fecha_generacion}}
```

> Usa nombres en `snake_case` y sin espacios — deben coincidir exactamente con el mapeo.

### Paso 2: Crea el escenario que lee el Sheet

En un escenario nuevo (`Reporte mensual de facturas`):
- Trigger: **Run once** por ahora (en la Sesión 6 lo haremos Scheduled).
- Agrega **Google Sheets › Search Rows** sobre `Facturas-Registro` (filtra por el mes en curso si quieres).

### Paso 3: Calcula los agregados

Con módulos de Make (o agregando una llamada a la IA):
- `total` → suma de la columna monto
- `top_proveedor` → el proveedor con mayor monto
- `num_facturas` → cantidad de filas

> Tip: el módulo **Tools › Numeric aggregator** suma; **Text aggregator** arma listas.

✓ **Verificación:** Tienes los valores calculados disponibles como variables.

### Paso 4: Genera el documento con la plantilla

Agrega **Google Slides › Create a Presentation from a Template**:
- **Template:** tu `Reporte-Facturas-Plantilla`
- **Destination:** una carpeta de Drive (`Reportes`)
- **Mapeo** de cada placeholder:
  - `{{mes}}` → `formatDate(now; "MMMM")`
  - `{{anio}}` → `formatDate(now; "YYYY")`
  - `{{total}}` → `"S/ " + formatNumber(total; 2)`
  - `{{top_proveedor}}` → variable del Paso 3
  - `{{num_facturas}}` → variable del Paso 3
  - `{{fecha_generacion}}` → `formatDate(now; "D [de] MMMM [de] YYYY")`

### Paso 5: Prueba y revisa

Corre **Run once** y abre el Slide generado en Drive. Verifica que todos los placeholders se reemplazaron y que el formato (moneda, fecha) se ve bien.

✓ **Verificación:** El Slide del reporte mensual tiene datos reales, sin placeholders sin reemplazar.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué pasa si el nombre de un placeholder no coincide exactamente con el mapeo?**
2. **¿Por qué conviene formatear el monto y la fecha antes de inyectarlos?**

---

## Logros Adicionales (Opcional)

### 🟢 Versión en Docs
Crea una segunda plantilla en Google Docs (carta o ficha) y genera el reporte también como Doc con Create a Document from Template.

### 🟡 Agrega un ranking
Suma un placeholder `{{ranking_proveedores}}` con el top 3 de proveedores por monto (usa un Text aggregator).

### 🔴 Envía el reporte por correo
Agrega Export as PDF + Gmail Send an Email para que el reporte llegue al correo. (Lo formalizamos en la Sesión 6.)

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] Plantilla en Slides con placeholders `{{variable}}`
- [ ] Escenario que lee el Sheet y calcula agregados
- [ ] Create from Template con cada placeholder mapeado
- [ ] Slide generado con datos reales y formato (moneda/fecha) correcto

> 📸 Ten a la mano el Slide generado en Drive y el escenario con el módulo Create from Template en verde.
