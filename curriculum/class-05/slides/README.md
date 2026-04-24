<!-- .slide: data-background="#0A192F" -->
# Clase 05: Gemini API + 2 flujos completos
## La IA entra al sistema — clase bisagra del curso

---

## TRANSICIÓN: Módulo 1 → Módulo 2

### Módulo 1 (Clases 1-4):
- Gem + brief + Sheet + Slides + 2 flujos en Make
- Sistema end-to-end **sin IA** en el flujo
- Marcadores tipo IA nombrados pero **vacíos**

### Hoy (bisagra al Módulo 2):
- Gemini API entra al flujo vía módulo HTTP
- Los marcadores tipo 3 dejan de estar vacíos
- Los dos escenarios quedan activos 24/7

> "Hasta hoy movías datos. Desde hoy, el sistema piensa."

---

## QUIZ PRE-LAB

### Pregunta:

Cuando leés un correo informal de un vendedor ("Hola, hoy Juan cerró con Industrias López por 3500 soles..."), ¿qué "datos" extraes mentalmente sin pensarlo?

*Toma 2-3 respuestas. Eso es exactamente lo que Gemini hará hoy.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Viste el primer test de la API. ¿Qué pasa si Gemini responde un texto que NO es JSON válido (ej: agrega un párrafo introductorio)?

A. Parse JSON lanza error y el flujo se detiene
B. Parse JSON salta el texto intro y procesa solo el JSON
C. Make convierte automáticamente cualquier respuesta a JSON
D. Gemini nunca responde nada que no sea JSON válido

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** A

**Análisis de opciones:**
- **A:** Correcto. Parse JSON espera un JSON puro; si recibe "Claro, aquí está: {...}" da error. Solución: prompt más estricto ("responde SOLO JSON, sin texto adicional").
- **B:** Falso. Parse JSON no es inteligente — falla si hay ruido.
- **C:** Falso. Make no "arregla" respuestas.
- **D:** Falso. Gemini a veces agrega prosa; por eso hay que ser explícito en el prompt.

> **Clave:** La palabra mágica del prompt es "SOLO JSON, sin texto adicional."

---

## CHECKPOINT Actividad 1: Gemini extrae datos de correos

### Verificar:
Cada estudiante envía 3 correos informales y muestra el Sheet.

**¿Qué debe verse?**
- 3 filas nuevas con todos los campos llenos
- Datos coherentes aunque los correos tengan formatos distintos
- Columna Descripción con resumen en 1 línea generado por Gemini

**Problemas comunes:**
- Parse JSON falla → prompt no fue estricto, agregar "responde SOLO en JSON"
- Campos vacíos → el correo no menciona ese dato; Gemini dejó null (OK)
- API key no funciona → verificar que se copió sin espacios, proyecto activo en AI Studio

---

## CHECKPOINT Actividad 2: Marcadores tipo IA llenos

### Verificar:
Cada estudiante corre Run once del Escenario 2 y muestra el PDF.

**¿Qué debe verse?**
- Al menos 3 marcadores tipo IA con texto coherente (no `{{hallazgo_1}}` literal)
- Texto específico a los datos del Sheet (menciona nombres, números)
- Formato PDF intacto (no desbordamiento por textos largos de Gemini)

**Problemas comunes:**
- Marcadores siguen literales → Replace Text no está mapeado al Parse JSON correcto
- Textos demasiado largos → agregar al prompt "máximo 25 palabras por campo"
- Gemini devuelve español con errores → agregar al prompt "responde en español latinoamericano"

---

## CHECKPOINT Actividad 3: Scheduled + Historico activos

### Verificar:
Ambos escenarios con toggle "On".

**¿Qué debe verse?**
- Escenario 1: Instant trigger activo, icono verde
- Escenario 2: Scheduled viernes 4pm, próxima ejecución visible
- Historico con fila nueva después del Run once

**Problemas comunes:**
- Scheduled no se activa → revisar zona horaria del escenario
- Historico no recibe fila → módulo Add a row al final no está conectado al flujo principal

---

## REFLEXIÓN: Consumo de operaciones con IA

| Escenario | Ops sin IA | Ops con IA | Mensuales (plan free) |
|-----------|-----------|-----------|----------------------|
| Captura correos (por correo) | 2 | 4 | ~240 correos/mes |
| Reporte semanal | 12 | 18 | ~55 reportes/mes |

> **Regla memorable:** "Agregar IA cuesta 2-6 ops extra — mínimo comparado con el valor que agrega."

---

## TRANSICIÓN: Preview Clase 06

### Hoy lograste:
- API key de Gemini configurada
- 2 escenarios activos con IA
- Marcadores tipo 3 llenos automáticamente
- Sistema modelo completo 24/7

### Próxima clase:
- Optimizar prompts con chain-of-thought, few-shot, persona
- Comparar insights "planos" vs "potentes"
- Aplicar 4 mejores prácticas del sistema
- Definir plan de personalización para TU caso

---

## Preguntas de Cierre

1. De los insights que Gemini generó, ¿cuál te pareció más útil? ¿Cuál más plano?

2. Si comparás el reporte de hoy con cómo lo armabas a mano antes del curso, ¿qué tiempo calcularías que ahorras por reporte?

3. ¿Qué marcador tipo IA crees que se beneficiará más de un prompt optimizado en Clase 6?

---

## Entrega

- Screenshots de ambos escenarios activos con módulos visibles
- PDF con marcadores tipo IA llenos
- Historico con fila nueva del test

### Próxima clase: Integración total + mejores prácticas
