# Rúbrica - Lab Módulo 1: Make básico — Tus primeros 2 flujos sin IA

> 📋 **Documento interno para evaluadores**
>
> ⚠️ El contenido debe coincidir exactamente con la sección "Rúbrica de Evaluación" de `lab/README.md`. Si actualizas uno, actualiza el otro.

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Proyecto** | Sistema automatizado de reportes (piezas integradas, sin IA todavía) |
| **Módulo** | 1 - Piezas del Sistema |
| **Clase** | 4 - Make básico (sin IA) |
| **Puntaje Total** | 100 puntos |

---

## Criterios de Evaluación

### 1. Escenario 1 — Gmail → Sheet (20 puntos)

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 20 | Instant Trigger activo, filtro de asunto específico a su caso, al menos 3 filas agregadas en la prueba con timestamps visibles |
| **Bueno** | 15 | Funciona pero sin filtro específico (captura cualquier correo) |
| **Satisfactorio** | 10 | Funciona en modo manual (Run once) o Scheduled, pero no Instant |
| **Bajo** | 5 | Configurado pero no llega a registrar filas |
| **No entregado** | 0 | Sin escenario 1 creado |

**Aspectos evaluados:**
- Trigger en modo Instant
- Filtro de asunto configurado
- Mapeo correcto de campos del correo a columnas del Sheet
- Evidencia de que el flujo procesó al menos 3 correos

---

### 2. Escenario 2 — Flujo del reporte (20 puntos)

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 20 | ≥8 marcadores reemplazados (tipo 1 y 2), PDF generado con diseño intacto |
| **Bueno** | 15 | 5-7 marcadores reemplazados |
| **Satisfactorio** | 10 | 3-4 marcadores reemplazados |
| **Bajo** | 5 | <3 marcadores o PDF no se genera correctamente |
| **No entregado** | 0 | Sin escenario 2 creado |

**Aspectos evaluados:**
- Search Rows leyendo Sheet correctamente
- Create from Template duplicando la plantilla de Clase 3
- Replace Text con marcadores en snake_case
- Export as PDF funcional
- Uso de módulos Date/Math para calculados

---

### 3. Entrega por Gmail (20 puntos)

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 20 | Correo llega con PDF adjunto, asunto descriptivo con fecha dinámica |
| **Bueno** | 15 | PDF llega pero asunto genérico o fijo |
| **Satisfactorio** | 10 | PDF generado en Drive pero no enviado por correo |
| **Bajo** | 5 | Correo llega sin adjunto o con error |
| **No entregado** | 0 | Sin módulo Send an Email |

**Aspectos evaluados:**
- Módulo Gmail Send an Email configurado
- PDF correctamente adjuntado
- Asunto informativo (no genérico)

---

### 4. Mejores prácticas — Desafío (20 puntos)

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 20 | Nombre con fecha + error handler + copia en carpeta Backups |
| **Bueno** | 15 | Nombre con fecha + error handler |
| **Satisfactorio** | 10 | Solo nombre con fecha dinámica |
| **Bajo** | 5 | Intento pero no funcional |
| **No entregado** | 0 | Sin mejoras aplicadas |

**Aspectos evaluados:**
- `formatDate(now; "YYYY-MM-DD")` en nombre de archivo
- Error handler con notificación por correo
- Respaldo automático en carpeta Backups

---

### 5. Tabla de parámetros actualizada (20 puntos)

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 20 | Documentados módulos de Make, mapeos, nombres de escenarios, triggers y mejoras |
| **Bueno** | 15 | Mapeos principales documentados, faltan detalles menores |
| **Satisfactorio** | 10 | Solo estructura básica del Sheet/Slides registrada |
| **Bajo** | 5 | Sin actualización post-lab |
| **No entregado** | 0 | No hay tabla de parámetros |

**Aspectos evaluados:**
- Sección "Make: Escenarios" con nombres y triggers
- Lista de módulos usados por escenario
- Mapeos de campos y marcadores documentados

---

## Escala de Calificación

| Rango | Nota | Descripción |
|-------|------|-------------|
| 90-100 | A | Excelente - Sistema end-to-end con mejores prácticas aplicadas |
| 80-89 | B | Bueno - Sistema funcional con mejoras menores pendientes |
| 70-79 | C | Satisfactorio - Cumple requisitos mínimos del Módulo 1 |
| < 70 | F | Necesita mejora - Seguimiento 1 a 1 antes del Módulo 2 |

---

## Checklist de Entrega

### Archivos Requeridos

- [ ] Screenshot del Escenario 1 activo en Make
- [ ] Screenshot del Sheet con filas agregadas automáticamente (con timestamps)
- [ ] Screenshot del Escenario 2 completo
- [ ] Screenshot del PDF llegando al correo con marcadores reemplazados
- [ ] Link compartido a carpeta "Proyecto de Instrucción" en Drive

### Documentación

- [ ] Tabla de parámetros actualizada con secciones Make (Escenarios, Módulos, Mapeos)

### Verificación Técnica

- [ ] Escenario 1 muestra toggle "On" (activo)
- [ ] Sheet tiene filas con fechas dentro de la última semana
- [ ] PDF tiene ≥5 marcadores reemplazados con datos reales
- [ ] Correo llegó al inbox del estudiante

---

## Notas para el Evaluador

1. **No penalizar marcadores tipo IA vacíos.** En Clase 4 todavía no se llenan. Solo evaluar tipos 1 y 2.
2. **Verificar que las filas del Sheet vengan del Instant Trigger.** Si están a mano, puntúa bajo en Criterio 1.
3. **El desafío es post-clase.** Si el estudiante entrega solo Actividades 1-3 en tiempo, puntúa bien los criterios 1-3 y marca el 4 según el estado real.
4. **La tabla de parámetros es el artefacto vivo del curso.** Su calidad en esta clase predice el éxito en los Módulos 2 (7-8).

---

## Ejemplo de Retroalimentación

### Retroalimentación Positiva
> "Excelente trabajo integrando las piezas del M1. Tu Instant Trigger está capturando correos con filtro específico, y el escenario 2 reemplaza 8 marcadores con cálculos precisos. La tabla de parámetros documenta todos los mapeos — listo para agregar IA en Clase 5."

### Áreas de Mejora
> "El flujo funciona end-to-end, pero el filtro de Gmail captura cualquier correo, no solo los de tu caso. En Clase 5 esto se volverá crítico porque Gemini empezará a procesar correos — necesitás un filtro específico para evitar procesar cosas no deseadas. Agrega `subject contains 'Ventas del día'` antes de la próxima sesión."
