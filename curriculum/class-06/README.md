> **Módulo 2:** Clase 2 de 4

# Clase 06: Integración total y mejores prácticas

## Resumen

El sistema modelo ya funciona con IA desde la Clase 5 — pero funciona "a nivel demo". Hoy lo profesionalizamos. Vas a optimizar los prompts que configuraste ayer para que los insights pasen de "planos" a "potentes", aplicando tres técnicas de prompt engineering: persona explícita, few-shot (ejemplos dentro del prompt) y chain-of-thought (pedir razonamiento paso a paso). La diferencia que vas a ver es dramática — mismo input, salida 10x más útil.

Después vas a aplicar **cuatro mejores prácticas** que convierten un sistema demo en un sistema de producción: nombres de archivo con fecha dinámica, carpeta de backups automática, alertas por correo si algo falla, y una pestaña de logs que registra cada ejecución. Al terminar, cerrarás la clase definiendo los 5 puntos críticos que vas a personalizar en la Clase 7, cuando el sistema deje de ser el de Roberto y sea el tuyo.

---

## ¿Por qué te sirve?

- **Un prompt optimizado genera insights que tu audiencia lee.** Un prompt mediocre genera insights que nadie abre. La diferencia es 15 minutos de optimización por prompt.
- **Sin las 4 mejores prácticas, el sistema falla silenciosamente en 2-3 meses.** Un error handler + logs + backups son la diferencia entre "funcionó 1 semana" y "funciona 2 años".
- **Los 5 puntos de personalización son el puente entre el caso Roberto y tu caso real.** Sin claridad en estos 5 puntos, la Clase 7 se vuelve improvisación.

---

## 🎯 ¿Qué haremos en clase?

1. **Exploraremos prompt engineering avanzado** - Descubrirás cómo persona + few-shot + chain-of-thought transforman outputs.
2. **Optimizarás tus prompts de producción** - Reescribirás 3 prompts clave y compararás antes/después lado a lado.
3. **Aplicarás 4 mejores prácticas** - Nombre con fecha, backups, alertas, logs. El sistema pasa de demo a producción.
4. **Definirás tu plan de personalización** - 5 puntos críticos que vas a cambiar en Clase 7 para adaptar al caso real.

---

## Objetivos de Aprendizaje

Al finalizar esta clase, podrás:

1. **Aplicar** chain-of-thought, few-shot y persona explícita en prompts de producción.
2. **Comparar** outputs de prompts "planos" vs "optimizados" con ejemplos concretos propios.
3. **Configurar** 4 mejores prácticas del sistema (fecha en nombres, backups, alertas, logs).
4. **Definir** 5 puntos críticos de personalización para adaptar el sistema modelo a tu caso real.

---

## ✅ Preparación para la Clase

### De clases anteriores

- Sistema modelo con IA funcionando (Clase 5): 2 escenarios activos con Gemini API
- Marcadores tipo IA llenándose automáticamente
- Tabla de parámetros con prompts documentados

### Reflexión previa

Antes de llegar a clase, reflexiona sobre:

- De los insights que Gemini generó ayer, ¿cuáles se sintieron "útiles" y cuáles "tibios"?
- Si tuvieras que adaptar el sistema a tu caso real, ¿qué sería lo primero que cambiarías?

### Herramientas

- [ ] **Los 2 escenarios de Make activos** de Clase 5
- [ ] **3-5 ejemplos de insights generados por Gemini** (tomar screenshots para comparar antes/después)
- [ ] **Tu brief original de Clase 1** — lo vas a revisitar para definir personalización

### Lectura sugerida

- [Guía de prompt engineering de Google](https://ai.google.dev/gemini-api/docs/prompting-strategies){:target="_blank"} - Estrategias oficiales.
- [Chain of thought — paper original](https://arxiv.org/abs/2201.11903){:target="_blank"} - Si querés ir a la fuente académica.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Chain of thought** | Técnica que pide a la IA "pensar paso a paso antes de responder" — mejora razonamiento. |
| **Few-shot** | Dar 2-3 ejemplos de input/output deseado dentro del prompt. Mejora consistencia. |
| **Persona** | Definir rol específico de la IA ("eres analista con 10 años de experiencia"). |
| **Storytelling de datos** | Contextualizar números: comparar contra meta, explicar causa, sugerir acción. |
| **Error handler** | Módulo de Make que se activa si un paso del flujo falla. |
| **Log** | Registro persistente de ejecuciones (fecha, estado, duración). |
| **Punto de personalización** | Aspecto específico del sistema que cambia según el caso del estudiante. |

---

## Recursos Adicionales

- [Error handlers en Make](https://www.make.com/en/help/errors/error-handling){:target="_blank"} - Cómo configurar manejo de errores.
- [Formateo de fechas en Make](https://www.make.com/en/help/functions/date-and-time-functions){:target="_blank"} - Referencia de `formatDate()`.
