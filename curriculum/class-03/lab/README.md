# Lab 03: Google Slides con IA

## 🎯 Objetivos

1. Diseñar una plantilla de Google Slides con 6 secciones del reporte ejecutivo usando tu Gem.
2. Nombrar y clasificar ~18-20 marcadores variables en la tabla de parámetros (tipo crudo/calculado/IA).
3. Insertar los marcadores en la plantilla y validar visualmente con una prueba manual.

---

## 🔑 Conceptos Clave

- **Anatomía del reporte ejecutivo** — 6 secciones: Portada, Resumen, Hallazgos, Visualización, Riesgos/Oportunidades, Próximos pasos.
- **3 tipos de marcadores** — Crudo (del Sheet), Calculado (de Make), Generado por IA (de Gemini).
- **Convención snake_case** — nombres descriptivos, sin espacios, agrupados por sección (`portada_titulo`, `resumen_ventas`).

---

## ⚙️ Setup Inicial

Esta sesión usa los artefactos de las clases anteriores. Verifica:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Sheet con 3 pestañas y datos | Puedes abrir `VentasSemanaActual` y ver las 15 filas |
| ☐ | Tabla de parámetros (Google Doc) | Tiene secciones de columnas y rangos registradas |
| ☐ | Gem del curso funcionando | Responde mencionando tu brief |

> ⚠️ Si no completaste el Sheet de la Clase 2, completa primero las 3 pestañas antes de continuar.

---

## Actividad 1: Diseña las 6 secciones del reporte (30 min)

### 1.1 Pide al Gem la estructura

Envía a tu Gem:

```
Según mi brief, dame las 6 secciones de mi reporte ejecutivo.
Para cada sección, dame: nombre, 1 línea de propósito, y qué
información debería mostrar. Usa como referencia la anatomía
clásica: portada, resumen, hallazgos, visualización, riesgos/oportunidades,
próximos pasos.
```

### 1.2 Crea la plantilla en Slides

Nombre del archivo:

```
Reporte [<!-- tu proyecto -->] — Plantilla
```

Crea 6 slides con estos títulos (ajusta a tu caso):

1. **Portada** — contexto, fecha, marca
2. **Resumen ejecutivo** — KPIs principales + narrativa
3. **Hallazgos** — 3 insights clave
4. **Visualización** — gráfico del período
5. **Riesgos y oportunidades** — qué cuidar, qué aprovechar
6. **Próximos pasos** — acciones concretas

### 1.3 Aplica paleta y tipografía

Pide al Gem:

```
Según mi industria y tipo de reporte, sugiere 2-3 colores
(paleta hex) y 2 tipografías de Google Fonts que transmitan
[<!-- ejecutivo, moderno, cercano, sobrio -->].
```

Aplica los colores al fondo/títulos y las tipografías al cuerpo.

✅ **Checkpoint:** Tu plantilla tiene 6 slides con títulos específicos a tu reporte y un estilo visual consistente.

---

## Actividad 2: Nombra todos los marcadores (45 min)

### 2.1 Identifica qué es variable

Slide por slide, subraya mentalmente qué texto cambia cada vez que corres el reporte. Esos son los marcadores.

### 2.2 Nombra cada marcador en snake_case

Reglas:
- Todo minúsculas
- Palabras separadas por guion bajo
- Descriptivo, no abreviado (`ventas_total_semana`, no `vts`)
- Agrupado por sección como prefijo (`portada_titulo`, `resumen_ventas`)

### 2.3 Clasifica por tipo en la tabla de parámetros

Agrega sección nueva a tu tabla de parámetros:

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
| `{{proximo_reporte}}` | Calculado | Make | "26-04-2026" |
| ... | ... | ... | ... |

**Meta:** ~18-20 marcadores clasificados.

### 2.4 Adapta a tu caso

Si tu caso no son ventas, cambia los nombres pero mantén la estructura. Ejemplos:

- Marketing: `{{alcance_total}}`, `{{engagement_promedio}}`, `{{campana_destacada}}`
- Consultoría: `{{horas_facturadas}}`, `{{proyectos_activos}}`, `{{cliente_mes}}`

✅ **Checkpoint:** Tu tabla de parámetros tiene entre 18-20 filas de marcadores, cada una con tipo y origen claros.

---

## Actividad 3: Inserta marcadores y prueba manual (25 min)

### 3.1 Reemplaza textos por marcadores en cada slide

En cada slide, reemplaza los textos placeholder por `{{marcadores}}` correspondientes.

Ejemplo de la slide de Resumen ejecutivo:

```
Esta semana generamos {{ventas_total}} soles,
un {{variacion_pct}} vs la semana anterior.
{{resumen_ejecutivo}}
```

### 3.2 Inserta el gráfico vinculado

**Insertar → Gráfico → Desde Hojas de cálculo** → selecciona tu Sheet → pestaña `VentasSemanaActual` → elige el gráfico que quieres mostrar.

> 💡 El gráfico se actualiza automáticamente cuando cambian los datos del Sheet.

### 3.3 Prueba manual

Elige 3-4 marcadores y reemplázalos a mano con datos reales para verificar que el diseño aguanta:

- `{{ventas_total}}` → `21,700`
- `{{clientes_nuevos}}` → `8`
- `{{hallazgo_1}}` → `Juan cerró 2 renovaciones grandes...`

### 3.4 Ajusta diseño

Si el texto queda cortado o desbordado, ajusta tamaños y espaciados. Cuando pongas los datos reales en Clase 4, no habrá tiempo de rediseñar.

✅ **Checkpoint:** Tu plantilla tiene todos los marcadores visibles, un gráfico vinculado al Sheet y la prueba manual muestra un diseño estable.

---

## 📁 Estructura Final del Proyecto

```
Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc
    ├── Tabla-de-Parámetros.doc  (crece con marcadores)
    ├── sistema-reporte.xlsx     (Sheet con 3 pestañas)
    └── Reporte-Plantilla.slides ← NUEVO (6 slides + marcadores)
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué marcador de tu plantilla crees que será el más difícil de llenar automáticamente?**
2. **¿Por qué conviene que los marcadores tipo IA (`hallazgo_1`, `riesgo_2`) estén nombrados aunque hoy estén vacíos?**
3. **¿Qué sección del reporte te parece la más valiosa para tu lector final?**

---

## Logros Adicionales (Opcional)

### 🟢 Duplica la plantilla antes de la próxima clase
Crea una copia llamada `Reporte-SemanaReal` y prueba llenar a mano TODOS los marcadores con datos reales de una semana pasada. Te prepara para Clase 4 cuando Make lo haga solo.

### 🟡 Agrega una slide de "Apéndice"
Slide 7 con una tabla de apéndice para detalles (top clientes, desglose por vendedor). Define 3-4 marcadores adicionales.

### 🔴 Diseña versión móvil
Una segunda plantilla formato vertical (para compartir por WhatsApp) con los 3 KPIs principales. Preview del reto de Clase 6 (optimización para canal).

---

## 📝 Entrega

### Checklist

- [ ] Plantilla de Google Slides con 6 slides diseñadas
- [ ] Tabla de parámetros con 18-20 marcadores clasificados
- [ ] Prueba manual exitosa (al menos 1 slide con datos reales)
- [ ] Gráfico vinculado al Sheet insertado

### Entregable

📸 **Screenshot** de la slide 2 (Resumen ejecutivo) de tu plantilla, donde se vean:
- Los marcadores `{{...}}` visibles en su posición
- El título de la plantilla en la barra superior
- Tu correo de Google visible en la esquina

> ⚠️ El entregable debe mostrar tu cuenta de Google para verificar que es tu plantilla.
