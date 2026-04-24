<!-- .slide: data-background="#0A192F" -->
# Clase 07: Tu proyecto propio
## El sistema deja de ser de Roberto y se vuelve tuyo

---

## TRANSICIÓN: Clase 06 → Clase 07

### Clase anterior:
- Prompts optimizados con persona + few-shot + CoT
- 4 mejores prácticas aplicadas
- Plan de personalización con 5 puntos listo

### Hoy:
- Acompañamiento 1 a 1 del instructor
- Construís TU sistema con TUS datos reales
- La arquitectura se queda, el cerebro cambia

> "La habilidad más valiosa del curso: transferir patrones a contextos nuevos."

---

## QUIZ PRE-LAB

### Pregunta:

Si tuvieras que escribir el SystemPrompt de TU caso en este momento, ¿qué palabra clave incluirías que NO está en el de Roberto?

*Toma 2-3 respuestas. Es calentamiento para la personalización.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Viste cómo el Escenario 2 se duplica vía Export/Import Blueprint. ¿Qué DEBE reconfigurarse después de importar el duplicado?

A. Nada — queda idéntico al original
B. Las conexiones (apuntan al Sheet/Slides nuevos) y los prompts (tu caso)
C. Solo las conexiones, los prompts se mantienen
D. Solo los prompts, las conexiones se mantienen

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** B

**Análisis de opciones:**
- **A:** Falso. El blueprint copia estructura pero apunta al Sheet/Slides originales.
- **B:** Correcto. Conexiones = a qué Sheet/Slides lee/escribe (debe ser tu v2). Prompts = contexto de Gemini (debe ser tu industria).
- **C:** Incompleto — si mantenés los prompts de Roberto, Gemini genera insights de ventas B2B aunque vos hagas marketing.
- **D:** Incompleto al revés — si las conexiones apuntan al Sheet viejo, no procesás tus datos.

> **Clave:** Duplicar un escenario = copiar el esqueleto. Adaptás los órganos después.

---

## CHECKPOINT Actividad 1: Sheet personalizado con datos reales

### Verificar:
Cada estudiante muestra su Sheet v2.

**¿Qué debe verse?**
- Pestañas con nombres de su caso (no `VentasSemanaActual` literal si no es ventas)
- Columnas específicas de su industria
- Datos reales (o simulados realistas) en las 3 pestañas
- Rangos nombrados actualizados

**Problemas comunes:**
- Sheet copiado pero sin renombrar pestañas → "solo cambiaste el nombre del archivo"
- Datos del caso Roberto todavía presentes → limpiar filas de ejemplo

---

## CHECKPOINT Actividad 2: Slides con marca + 2 escenarios duplicados

### Verificar:
Plantilla v2 + 2 escenarios v2 visibles en Make.

**¿Qué debe verse?**
- Logo, colores y tipografías propias en Slides
- Marcadores renombrados (o razonables) según caso
- Escenarios v2 activos y apuntando al Sheet/Slides v2
- Prompts del HTTP mencionan tu industria

**Problemas comunes:**
- Escenario v2 sigue apuntando al Sheet viejo → actualizar Search Rows y Add a row
- Prompt de Gemini dice "ventas" aunque el caso es marketing → personalizar el SystemPrompt

---

## CHECKPOINT Actividad 3: Validación end-to-end con datos reales

### Verificar:
PDF generado con datos reales del estudiante.

**¿Qué debe verse?**
- Logo propio en portada
- Marcadores llenos con datos reales (no simulados)
- Insights tipo IA mencionando nombres/métricas específicas a tu caso
- Diseño visual respetado

**Problemas comunes:**
- Insights siguen genéricos → el SystemPrompt del Escenario 2 no se actualizó
- Replace Text no funciona → marcadores renombrados en Slides pero viejos en Make
- PDF desbordado → ajustar tamaños de texto (Gemini puede generar respuestas largas)

---

## REFLEXIÓN: Lo que cambia vs lo que se queda

| Se queda | Cambia |
|----------|--------|
| Arquitectura (Gmail → Sheet → Slides → PDF → Gmail) | Nombres de pestañas y columnas |
| Patrón de 3 pestañas | Columnas específicas |
| Estructura de prompt (Persona + Contexto + Reglas + Ejemplo) | Contenido de cada bloque |
| 4 mejores prácticas | Marca y destinatarios |

> **Regla memorable:** "El patrón se queda. El contenido cambia. Esa es la transferencia."

---

## TRANSICIÓN: Preview Clase 08

### Hoy lograste:
- Sistema propio funcionando con datos reales
- Marca aplicada en Slides
- Prompts adaptados a tu industria
- PDF del reporte llegando a tu correo

### Próxima clase:
- Demo Day — presentás tu sistema en 5 min
- Cálculo de ROI (horas × tarifa)
- Plan 30 días con 3 próximas automatizaciones
- Cierre del curso

---

## Preguntas de Cierre

1. ¿Qué parte de la transferencia fue más fácil de lo que esperabas? ¿Cuál más difícil?

2. Si ajustás tu sistema 1 hora cada mes, ¿cuánto tiempo te ahorrará al año? Haz la cuenta rápida.

3. ¿Qué demo de 2 minutos vas a preparar para la Clase 8 que muestre el impacto más claro?

---

## Entrega

- Screenshots de Sheet v2, Slides v2, 2 escenarios v2
- PDF del reporte con datos reales
- Sistema listo para Demo Day

### Próxima clase: Demo Day + ROI + Plan 30 días
