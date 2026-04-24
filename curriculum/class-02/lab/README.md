# Lab 02: Google Sheets con IA

## 🎯 Objetivos

1. Diseñar una pestaña operativa (`VentasSemanaActual`) con columnas coherentes y 15 filas de ejemplo generadas con Gemini.
2. Construir una pestaña `Config` con los parámetros del negocio (meta, equipo, categorías).
3. Cerrar con una pestaña `Historico` y 3 rangos nombrados documentados en la tabla de parámetros.

---

## 🔑 Conceptos Clave

- **Arquitectura de 3 pestañas** — operación + configuración + histórico. Cada una tiene un propósito claro.
- **Rango nombrado** — apodo que sobrevive a cambios de layout; Make los usa en vez de coordenadas `A1:G50`.
- **Tabla de parámetros** — documento vivo donde registras columnas, rangos y decisiones del sistema.

---

## ⚙️ Setup Inicial

Esta sesión continúa el proyecto de instrucción. Verifica que tengas todo listo:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Gem del curso funcionando | Responde a "Resume mi brief en una línea" mencionando tu proyecto |
| ☐ | Brief del proyecto en Google Doc | Carpeta "Proyecto de Instrucción" en Drive |
| ☐ | Tabla de parámetros (Google Doc) | Crear nuevo Doc con el título "Tabla de Parámetros — [tu proyecto]" |

> ⚠️ Si no completaste el Gem de la Clase 1, agrégalo antes de continuar. Sin él, no podrás pedir sugerencias contextualizadas al diseñar el Sheet.

---

## Actividad 1: Diseña la pestaña VentasSemanaActual (40 min)

### 1.1 Crea un Google Sheet nuevo

Nombre del archivo:

```
Sistema [<!-- tu proyecto -->] — [<!-- tu nombre -->]
```

Renombra la primera pestaña a `VentasSemanaActual`. Si tu caso no son ventas, usa el nombre que corresponda (`CampanasSemanaActual`, `CohortesSemana`, etc.) — el patrón es `[Entidad]SemanaActual`.

### 1.2 Pide columnas al Gem

Abre tu Gem y envía:

```
Según mi brief, dame las columnas para la pestaña operativa del Sheet
donde se capturarán los datos del día a día. Incluye una columna
"Descripción" para capturar contexto en 1 línea. Dame también el
tipo de dato por columna.
```

Como mínimo obligatorio, la pestaña debe tener:

| Columna | Tipo | Propósito |
|---------|------|-----------|
| Fecha | Fecha | Cuándo ocurrió el evento |
| [<!-- Quién registra -->] | Texto | Autor del dato (vendedor, autor, responsable) |
| [<!-- Entidad principal -->] | Texto | Cliente, campaña, proyecto, etc. |
| [<!-- Subcategoría -->] | Texto | Producto, canal, módulo, etc. |
| [<!-- Métrica numérica -->] | Número | Monto, alcance, horas |
| Tipo | Texto | Nuevo / Recurrente (o equivalente) |
| Descripción | Texto | Contexto en 1 línea (CLAVE para Gemini en clase 5) |

### 1.3 Genera 15 filas de ejemplo con el Gem

Envía al Gem:

```
Genera 15 filas de datos de ejemplo realistas para la pestaña
VentasSemanaActual con las columnas anteriores. Úsalas en formato TSV
(separado por tabulaciones) para pegar directamente en Sheets.
```

Copia-pega la respuesta en el Sheet. Ajusta tipos si hace falta.

### 1.4 Registra las columnas en la tabla de parámetros

Abre la tabla de parámetros y agrega:

| Categoría | Item | Valor |
|-----------|------|-------|
| Sheet: pestaña operativa | Nombre | `VentasSemanaActual` |
| Sheet: pestaña operativa | Columnas | [<!-- lista separada por comas -->] |

✅ **Checkpoint:** Tu Sheet tiene la pestaña `VentasSemanaActual` con las 7 columnas y 15 filas de ejemplo realistas. La tabla de parámetros registra el nombre y columnas.

---

## Actividad 2: Construye la pestaña Config (25 min)

### 2.1 Crea la pestaña Config

En tu Sheet, agrega una pestaña nueva llamada `Config`. Va a funcionar como "archivo de parámetros" del sistema.

### 2.2 Pide al Gem los parámetros del negocio

```
¿Qué parámetros de configuración necesita un reporte semanal según mi brief?
Dame una tabla con columnas: Parámetro, Valor (de ejemplo), Tipo de dato.
```

Como referencia (caso Roberto):

| Parámetro | Valor | Tipo de dato |
|-----------|-------|--------------|
| Meta semanal | S/ 20,000 | Número |
| Ticket promedio objetivo | S/ 2,800 | Número |
| Vendedores del equipo | Juan, María, Carlos, Ana | Texto (lista) |
| Meta por vendedor | S/ 5,000 | Número |
| % objetivo clientes nuevos | 30 | Porcentaje |

### 2.3 Reemplaza con valores reales

Usa los valores de TU negocio. Si no los tienes exactos, estima — después los refinas en la Clase 7.

### 2.4 Registra en la tabla de parámetros

Agrega sección:

| Categoría | Item | Valor |
|-----------|------|-------|
| Sheet: pestaña config | Nombre | `Config` |
| Sheet: pestaña config | Parámetros | [<!-- lista -->] |

✅ **Checkpoint:** La pestaña `Config` tiene al menos 4 parámetros del negocio con valores reales. La tabla de parámetros los registra.

---

## Actividad 3: Construye Historico y rangos nombrados (35 min)

### 3.1 Crea la pestaña Historico

En tu Sheet, agrega la pestaña `Historico`.

### 3.2 Pide al Gem las métricas a acumular

```
¿Qué métricas debo guardar semana a semana para comparar el desempeño
de mi reporte? Dame una tabla con: Columna, Fórmula (si aplica),
Explicación.
```

Columnas típicas:

| Semana | Ventas_Total | Clientes_Nuevos | Ticket_Promedio | Meta_Cumplida_Pct |
|--------|-------------|-----------------|-----------------|-------------------|

### 3.3 Llena 2-3 filas con datos simulados

Usa datos de semanas pasadas reales o inventados para tener material de prueba en la Clase 4.

### 3.4 Define los 3 rangos nombrados

En el menú: **Datos → Rangos con nombre → + Añadir un rango**.

```
RangoVentas    →  VentasSemanaActual!A:G
RangoConfig    →  Config!A:C
RangoHistorico →  Historico!A:E
```

### 3.5 Actualiza la tabla de parámetros

Agrega sección final:

| Categoría | Item | Valor |
|-----------|------|-------|
| Sheet: pestaña histórica | Nombre | `Historico` |
| Sheet: pestaña histórica | Columnas | Semana, Ventas_Total, ... |
| Sheet: rangos nombrados | `RangoVentas` | `VentasSemanaActual!A:G` |
| Sheet: rangos nombrados | `RangoConfig` | `Config!A:C` |
| Sheet: rangos nombrados | `RangoHistorico` | `Historico!A:E` |

✅ **Checkpoint:** Tu Sheet tiene 3 pestañas funcionando (con datos) y 3 rangos nombrados visibles en **Datos → Rangos con nombre**. La tabla de parámetros los documenta.

---

## 📁 Estructura Final del Proyecto

```
Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc
    ├── Tabla-de-Parámetros.doc   ← NUEVO
    └── sistema-reporte.xlsx       ← El Sheet
        ├── VentasSemanaActual (pestaña operativa + 15 filas)
        ├── Config (pestaña parámetros)
        └── Historico (pestaña memoria + 2-3 filas)
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Cuál de las 3 pestañas crees que será la más difícil de mantener actualizada en tu trabajo real?**
2. **¿Qué beneficio ves en separar datos de configuración de datos operativos?**
3. **¿Qué pregunta te quedó sobre cómo Make conectará con este Sheet la próxima clase?**

---

## Logros Adicionales (Opcional)

### 🟢 Agrega validación de datos
En la columna Tipo de `VentasSemanaActual`, agrega validación con lista desplegable (Datos → Validación de datos) con opciones "Nuevo" y "Recurrente". Esto evita inconsistencias cuando Gemini procese descripciones.

### 🟡 Diseña un gráfico dinámico
Inserta un gráfico que se actualice automáticamente con la columna Monto de `VentasSemanaActual`. En la Clase 3 lo vincularás con Slides.

### 🔴 Prepara el formato para Historico automático
Diseña fórmulas que tomarán los totales de `VentasSemanaActual` para que en la Clase 5 solo copiemos valores al Historico. Preview de la próxima clase.

---

## 📝 Entrega

### Checklist

- [ ] Google Sheet con 3 pestañas (`VentasSemanaActual`, `Config`, `Historico`) funcionando
- [ ] 15 filas de ejemplo en la pestaña operativa
- [ ] 3 rangos nombrados definidos (`RangoVentas`, `RangoConfig`, `RangoHistorico`)
- [ ] Tabla de parámetros actualizada en Google Doc

### Entregable

📸 **Screenshot** de la ventana **Datos → Rangos con nombre** mostrando:
- Los 3 rangos nombrados visibles
- El nombre del archivo del Sheet visible en la pestaña del navegador
- Tu correo de Google visible (esquina superior derecha)

> ⚠️ El entregable debe mostrar tu cuenta de Google para verificar que es tu Sheet.
