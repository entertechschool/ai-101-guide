<!-- .slide: data-background="#0A192F" -->
# Clase 02: Google Sheets con IA
## Diseña la fuente de datos de tu sistema

---

## TRANSICIÓN: Clase 01 → Clase 02

### Clase anterior:
- Creaste tu Gem con brief + archivo
- Practicaste prompts profesionales

### Hoy:
- Tu Gem pasa de asistente conceptual a copiloto de diseño de datos
- Dejas listo un Sheet con 3 pestañas para Make (Clase 4)

> "La IA no automatiza datos desordenados — los desordena más rápido."

---

## QUIZ PRE-LAB

### Pregunta:

¿Por qué separar parámetros del negocio (meta, equipo) en una pestaña distinta a los datos operativos? ¿Qué problema se evita?

*Toma 2-3 respuestas antes de continuar.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Viste que Make leerá el Sheet usando rangos nombrados (`RangoVentas`) en vez de coordenadas (`A1:G50`). ¿Por qué importa?

A. Porque los rangos nombrados son más rápidos de leer para Make
B. Porque evita romper el flujo si alguien agrega/reordena columnas
C. Porque solo los rangos nombrados permiten filtrar datos
D. Porque Make no puede leer coordenadas tradicionales

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** B

**Análisis de opciones:**
- **A:** El desempeño es igual. El beneficio es de mantenibilidad, no velocidad.
- **B:** Correcto. Si usas `A1:G50` y agregas una columna, Make sigue leyendo G pero perdiste información. Con rango nombrado, el rango crece automáticamente.
- **C:** Los filtros funcionan con cualquier referencia.
- **D:** Make lee ambos formatos. La diferencia es robustez, no compatibilidad.

> **Clave:** Los rangos nombrados hacen tu automatización inmune a cambios visuales del Sheet.

---

## CHECKPOINT Actividad 1: Pestaña operativa con 15 filas

### Verificar:
Cada estudiante muestra su pestaña `VentasSemanaActual` en pantalla.

**¿Qué debe verse?**
- 7 columnas con nombres específicos (no "Columna A")
- 15 filas con datos realistas generados por Gemini
- Columna "Descripción" presente y con texto en 1 línea

**Problemas comunes:**
- Columnas vagas ("Dato 1", "Info") → pedir al Gem que sea específico según el brief
- Datos genéricos copiados literal → el Gem los personaliza si le recuerdas el brief

---

## CHECKPOINT Actividad 2: Pestaña Config con parámetros reales

### Verificar:
Cada estudiante muestra su pestaña `Config`.

**¿Qué debe verse?**
- Al menos 4 parámetros con valores (no en blanco)
- Valores en unidades reales (S/, %, número de personas)
- Parámetros del negocio del estudiante, no del caso Roberto literal

**Problemas comunes:**
- Copiaron el ejemplo de Roberto sin adaptar → preguntar por su contexto real
- Parámetros vagos ("muchas ventas") → pedir número concreto, aunque sea estimado

---

## CHECKPOINT Actividad 3: 3 pestañas + rangos nombrados

### Verificar:
**Datos → Rangos con nombre** muestra 3 entradas.

**¿Qué debe verse?**
- `RangoVentas`, `RangoConfig`, `RangoHistorico` visibles
- Cada uno apunta a la pestaña correcta con columnas correctas
- Pestaña `Historico` tiene al menos 2 filas de datos simulados

**Problemas comunes:**
- Rango apunta a `A1:G50` (coordenadas fijas) → reemplazar con `A:G` (columna completa)
- Nombre del rango no es descriptivo → renombrar para que sea legible en Make

---

## REFLEXIÓN: Dato operativo vs dato de configuración

| Aspecto | Dato operativo | Dato de configuración |
|---------|----------------|-----------------------|
| **Frecuencia de cambio** | Varias veces al día | 1 vez al mes o menos |
| **Origen** | Correos, formularios | Decisión gerencial |
| **Ejemplo (Roberto)** | Venta registrada | Meta semanal |
| **Dónde vive** | `VentasSemanaActual` | `Config` |

> **Regla memorable:** "Lo que cambia seguido vive en operativa. Lo que define el negocio vive en Config."

---

## TRANSICIÓN: Preview Clase 03

### Hoy lograste:
- Sheet con 3 pestañas estructuradas
- 15 filas de ejemplo + 3 rangos nombrados
- Tabla de parámetros iniciada

### Próxima clase:
- Diseñar plantilla de Slides con 6 secciones
- Nombrar 18-20 marcadores que se conectarán a este Sheet
- Tabla de parámetros crece con marcadores clasificados por tipo

---

## Preguntas de Cierre

1. ¿Qué columna de tu pestaña operativa va a ser la más importante para que Gemini genere buenos insights?

2. ¿Qué parámetro de Config crees que cambiará primero cuando adaptes el sistema a tu caso real (Clase 7)?

3. Si tuvieras que explicarle a un colega por qué usas rangos nombrados, ¿cómo lo dirías en una frase?

---

## Entrega

- Sheet con 3 pestañas y datos de ejemplo
- 3 rangos nombrados definidos
- Tabla de parámetros actualizada

### Próxima clase: Google Slides con IA
