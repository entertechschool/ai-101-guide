<!-- .slide: data-background="#0A192F" -->
# Clase 06: Integración total y mejores prácticas
## De sistema demo a sistema de producción

---

## TRANSICIÓN: Clase 05 → Clase 06

### Clase anterior:
- Gemini API integrada en los 2 flujos
- Marcadores tipo IA llenándose automáticamente
- Sistema modelo activo 24/7

### Hoy:
- Prompts pasan de "planos" a "potentes" (10x calidad)
- Sistema pasa de demo a producción (backups, alertas, logs)
- Preparamos la transición a TU caso real

> "El sistema de ayer funcionaba. El sistema de hoy dura."

---

## QUIZ PRE-LAB

### Pregunta:

De los insights que Gemini generó ayer, ¿cuáles sentiste que eran útiles y cuáles tibios? ¿Qué les faltaba a los tibios?

*Toma 2-3 respuestas. Pista: números concretos, comparación, causa, acción.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Acabas de ver el mismo dato generado por 2 prompts distintos. ¿Qué 3 cosas tiene el insight "potente" que NO tiene el "plano"?

A. Emojis, colores, negritas
B. Números, comparación contra algo, causa probable
C. Más palabras en general
D. Referencias bibliográficas

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** B

**Análisis de opciones:**
- **A:** Forma, no fondo. Un insight potente sin formato sigue siendo potente.
- **B:** Correcto. Los 3 pilares del storytelling de datos: números, contexto, causa.
- **C:** Al revés — un insight potente puede ser más corto (más denso).
- **D:** No es reporte académico; es ejecutivo.

> **Clave:** Potente = datos + comparación + causa + acción. Si falta alguno, está tibio.

---

## CHECKPOINT Actividad 1: Prompts optimizados con antes/después

### Verificar:
Cada estudiante muestra 2 PDFs (C05 vs C06).

**¿Qué debe verse?**
- Insights de C06 con números específicos (no "las ventas fueron bien")
- Al menos 1 comparación (vs meta o vs anterior) por hallazgo
- Acciones ejecutables (no "mejorar ventas" sino "programar 1:1 con Juan")

**Problemas comunes:**
- Prompt v2 copiado literal sin adaptar al caso → personalizar el contexto
- Gemini sigue dando insights planos → verificar que el few-shot (ejemplo) está incluido

---

## CHECKPOINT Actividad 2: 4 mejores prácticas activas

### Verificar:
Sistema con las 4 aplicadas.

**¿Qué debe verse?**
- Nombre de PDF con fecha (ej: `Reporte_2026-04-19.pdf`)
- Carpeta Backups con al menos 1 PDF
- Error handler visible en el módulo HTTP
- Pestaña `Logs` con columnas correctas

**Problemas comunes:**
- `formatDate` con sintaxis incorrecta → copiar exacto: `{{formatDate(now; "YYYY-MM-DD")}}`
- Error handler no se activa → debe estar en modo "Resume" no "Rollback"
- Logs no recibe fila → conectar el Add a row al flujo principal al final

---

## CHECKPOINT Actividad 3: Plan personalización con 5 puntos

### Verificar:
Tabla de parámetros con nueva sección "Plan C7".

**¿Qué debe verse?**
- 5 puntos identificados con "Caso Roberto → TU caso"
- Versión "Tu caso" de marcadores clave
- Preview del proyecto de C7 en 2-3 líneas

**Problemas comunes:**
- Los 5 puntos son iguales a Roberto → el estudiante no terminó de traducir a su caso
- "Mi caso es igual" → probablemente no lo pensó; pedir ejemplo específico

---

## REFLEXIÓN: Demo vs Producción

| Aspecto | Sistema Demo | Sistema de Producción |
|---------|--------------|----------------------|
| **Dura** | 1 semana | Años |
| **Falla silenciosamente** | Sí | No (alertas) |
| **Recupera datos** | No | Sí (backups) |
| **Se audita** | Imposible | Fácil (logs) |
| **Tiempo de setup** | 0 min | +30 min (lo de hoy) |

> **Regla memorable:** "Una hora invertida en mejores prácticas ahorra un mes de debug futuro."

---

## TRANSICIÓN: Preview Clase 07

### Hoy lograste:
- Prompts optimizados con persona + few-shot + CoT
- Sistema de producción con 4 mejores prácticas
- Plan de personalización con 5 puntos

### Próxima clase:
- Acompañamiento 1 a 1 del instructor
- Construyes TU sistema con TUS datos reales
- El caso Roberto se queda atrás — ahora es tu trabajo

---

## Preguntas de Cierre

1. ¿Cuál de los 5 puntos de personalización te entusiasma más?

2. Si en 3 meses alguien más en tu equipo tuviera que entender tu sistema, ¿qué le dirías que lea primero?

3. De las 4 mejores prácticas, ¿cuál vas a implementar YA en otros sistemas de tu trabajo?

---

## Entrega

- 2 PDFs lado a lado (antes/después del prompt)
- Screenshot de Logs con ejecuciones
- Error handler configurado
- Plan personalización en tabla de parámetros

### Próxima clase: Tu proyecto propio (acompañamiento 1 a 1)
