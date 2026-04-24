<!-- .slide: data-background="#0A192F" -->
# Clase 03: Google Slides con IA
## Diseña la plantilla del reporte con marcadores

---

## TRANSICIÓN: Clase 02 → Clase 03

### Clase anterior:
- Sheet con 3 pestañas y 15 filas de ejemplo
- 3 rangos nombrados listos para Make
- Tabla de parámetros iniciada

### Hoy:
- Plantilla visual del reporte con marcadores
- 18-20 marcadores nombrados y clasificados por tipo
- Tabla de parámetros crece con la información clave del sistema

> "Un reporte ejecutivo bien diseñado es 80% plantilla fija y 20% datos variables."

---

## QUIZ PRE-LAB

### Pregunta:

Si tuvieras que dividir tu reporte actual en "partes que cambian siempre" vs "partes que siempre son iguales", ¿cuáles serían las partes que cambian?

*Toma 2-3 respuestas antes de continuar.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Acabas de ver la clasificación de marcadores en 3 tipos (crudo, calculado, IA). ¿Por qué importa distinguirlos HOY si todavía no los llenamos automáticamente?

A. Porque es una convención académica estándar
B. Porque los tipos definen qué herramienta llenará cada uno (Sheet/Make/Gemini)
C. Porque así se ven más organizados en Slides
D. Porque los marcadores tipo IA necesitan colores distintos

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** B

**Análisis de opciones:**
- **A:** No es solo convención. Sin tipo, no sabés dónde configurar cada marcador.
- **B:** Correcto. En la Clase 4, Make lee marcadores crudos del Sheet. En Clase 5, las HTTP requests de Gemini llenan los tipo IA. Cada tipo = configuración distinta.
- **C:** La visibilidad en Slides es la misma para los 3 tipos.
- **D:** No hay diferencia visual necesaria; sí hay diferencia operativa.

> **Clave:** Clasificar marcadores hoy evita confusión operativa en las clases 4 y 5.

---

## CHECKPOINT Actividad 1: 6 slides con diseño inicial

### Verificar:
Cada estudiante muestra su plantilla con 6 slides.

**¿Qué debe verse?**
- 6 slides distintas con títulos descriptivos (no "Slide 1", "Slide 2")
- Paleta consistente (2-3 colores)
- Tipografías legibles y consistentes

**Problemas comunes:**
- Títulos genéricos → recordar que las 6 secciones tienen nombres específicos
- Diseño muy denso → aplicar "1 slide = 1 idea"

---

## CHECKPOINT Actividad 2: ~18-20 marcadores clasificados

### Verificar:
Tabla de parámetros en Google Doc con sección de marcadores.

**¿Qué debe verse?**
- Al menos 18 filas de marcadores
- Cada fila tiene tipo (crudo/calculado/IA) y origen
- Nombres en snake_case (no espacios ni mayúsculas)

**Problemas comunes:**
- Solo 5-6 marcadores → revisar slide por slide qué más cambia
- Tipo IA confundido con crudo → crudo viene de una celda; IA se genera a partir de muchas celdas

---

## CHECKPOINT Actividad 3: Plantilla con marcadores + prueba

### Verificar:
Cada slide tiene marcadores insertados.

**¿Qué debe verse?**
- Marcadores `{{...}}` visibles en cada slide
- Gráfico vinculado al Sheet presente
- Al menos 1 slide con prueba manual (datos reales reemplazando 3-4 marcadores)

**Problemas comunes:**
- Marcadores con espacios (`{{ventas total}}`) → Replace Text es sensible, usar snake_case
- Gráfico insertado como imagen estática → debe ser "Desde Hojas de cálculo"

---

## REFLEXIÓN: Los 3 tipos de marcadores

| Tipo | Viene de | Ejemplo | Configuración en Make |
|------|----------|---------|------------------------|
| **Crudo** | Sheet (celda) | `{{ventas_total}}` | Search Rows → variable |
| **Calculado** | Make (fórmula) | `{{variacion_pct}}` | Módulo Math |
| **IA** | Gemini (prompt) | `{{hallazgo_1}}` | HTTP module + prompt |

> **Regla memorable:** "El nombre del marcador es para el lector. El tipo es para el sistema."

---

## TRANSICIÓN: Preview Clase 04

### Hoy lograste:
- Plantilla de Slides con 6 secciones
- 18-20 marcadores clasificados y documentados
- Gráfico vinculado al Sheet

### Próxima clase:
- Construir 2 flujos en Make (todavía sin IA)
- Gmail → Sheet en tiempo real
- Sheet → Slides → PDF → Gmail
- Los marcadores crudos y calculados empezarán a llenarse solos

---

## Preguntas de Cierre

1. ¿Qué slide de tu plantilla crees que va a impactar más a tu lector? ¿Por qué?

2. De tus marcadores tipo IA, ¿cuál crees que Gemini va a ser mejor generando? ¿Cuál peor?

3. Si tuvieras que explicarle en 1 frase a un colega para qué es la tabla de parámetros, ¿qué dirías?

---

## Entrega

- Plantilla con 6 slides y marcadores insertados
- Tabla de parámetros con 18-20 marcadores clasificados
- Prueba manual en al menos 1 slide

### Próxima clase: Make básico (sin IA)
