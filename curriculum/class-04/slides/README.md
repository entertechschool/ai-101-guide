<!-- .slide: data-background="#0A192F" -->
# Clase 04: Make básico (sin IA)
## Tus primeros 2 flujos — el sistema cobra vida

---

## TRANSICIÓN: Clase 03 → Clase 04

### Clase anterior:
- Plantilla de Slides con 6 secciones
- 18-20 marcadores nombrados y clasificados
- Tabla de parámetros completa

### Hoy:
- Conectás Gmail + Sheet + Slides en Make
- Primer "efecto WOW": correo → Sheet en 5 segundos
- Reporte PDF en tu correo con marcadores reales (sin IA aún)

> "Make es la herramienta que hace que las piezas dejen de ser artefactos y se vuelvan sistema."

---

## QUIZ PRE-LAB

### Pregunta:

Si pudieras automatizar solo UNA tarea de tu trabajo esta semana, ¿cuál sería y por qué?

*Toma 2-3 respuestas antes de continuar. Anotalo — es material para el proyecto de Clase 7.*

---

## COMPROBACIÓN

### Pregunta (después de la demo):

Acabas de ver un correo activando el Sheet en 5 segundos vía Instant Trigger. ¿Por qué NO serviría Scheduled (cada 15 min) para este caso?

A. Porque Scheduled consume más operaciones de Make
B. Porque 15 min es demasiado para efecto WOW en vivo
C. Porque Scheduled no puede leer Gmail
D. A y B son ciertas

---

## COMPROBACIÓN - Respuesta

**Respuesta correcta:** B (y parcialmente A)

**Análisis de opciones:**
- **A:** Parcialmente cierto — Scheduled cada 15 min = 96 ops/día solo por esperar. Instant solo consume cuando hay correo.
- **B:** Correcto principal. Si el jefe envía el correo y el Sheet se actualiza 15 min después, no hay "magia" visible.
- **C:** Falso. Scheduled también puede leer Gmail, solo que revisa cada X tiempo en vez de reaccionar.
- **D:** B es la razón principal. A es consecuencia.

> **Clave:** Instant = reacción en segundos. Scheduled = revisión periódica. Elegí según si necesitás "en vivo" o "eventualmente".

---

## CHECKPOINT Actividad 1: Gmail → Sheet funcionando

### Verificar:
Cada estudiante envía un correo y muestra el Sheet actualizarse.

**¿Qué debe verse?**
- Toggle "On" del escenario visible
- Filtro de asunto configurado
- Fila nueva en el Sheet con timestamp dentro de 10 segundos del envío

**Problemas comunes:**
- Sin filtro de asunto → captura TODOS los correos (agotan operaciones rápido)
- Filtro con tilde/caracteres especiales → simplificar a palabras simples
- Cuenta de Gmail con 2FA sin App Password → reconectar con credenciales alternativas

---

## CHECKPOINT Actividad 2: Sheet → Slides → PDF

### Verificar:
Corren Run once y muestran la plantilla duplicada con valores reales.

**¿Qué debe verse?**
- Al menos 5 marcadores reemplazados con datos del Sheet
- Al menos 1 marcador calculado (con módulo Date o Math)
- PDF generado en Drive

**Problemas comunes:**
- Marcador no se reemplaza → verificar que el texto exacto coincide (mayúsculas, espacios)
- Gráfico no aparece → en Slides debe ser "vinculado al Sheet", no imagen estática
- Replace Text se salta filas → mapear output del módulo anterior correctamente

---

## CHECKPOINT Actividad 3: Correo con PDF llegando

### Verificar:
Bandeja de entrada con correo del sistema.

**¿Qué debe verse?**
- Correo con asunto descriptivo (no "Re: ...")
- PDF adjunto con marcadores reemplazados
- Diseño de la plantilla respetado (sin marcadores sueltos)

**Problemas comunes:**
- PDF adjunto vacío o corrupto → revisar operación "Export as PDF"
- Correo no llega → verificar que el campo "To" tiene un correo válido y no el webhook
- Marcadores tipo IA muestran `{{hallazgo_1}}` literal → normal, los llenamos en Clase 5

---

## REFLEXIÓN: Instant vs Scheduled

| Aspecto | Instant Trigger | Scheduled Trigger |
|---------|-----------------|-------------------|
| **Latencia** | 2-5 segundos | 15 min - 1 día |
| **Consumo ops** | Solo cuando hay evento | Cada corrida, aunque esté vacío |
| **Cuándo usar** | Reacción en vivo | Consolidación periódica |
| **Ejemplo** | Correo → Sheet | Reporte semanal |

> **Regla memorable:** "Instant es para reaccionar. Scheduled es para agendar."

---

## TRANSICIÓN: Preview Clase 05

### Hoy lograste:
- 2 escenarios de Make funcionando
- Instant Trigger con efecto WOW
- Sistema end-to-end sin IA (todavía)
- Lab calificado del M1 completo

### Próxima clase:
- Primera vez conectás Gemini API en Make
- Los marcadores tipo IA dejan de estar vacíos
- Los correos informales se convierten en JSON estructurado
- Fin de Fase 1 → inicio de Fase 2

---

## Preguntas de Cierre

1. ¿Qué te sorprendió más hoy: la velocidad del Instant Trigger o que funcionó sin IA?

2. ¿Qué marcador tipo IA te da más curiosidad ver llenarse automáticamente en la Clase 5?

3. Si mañana tu flujo actual dejara de funcionar, ¿cuál sería la primera cosa que revisarías?

---

## Entrega

- Screenshots del Escenario 1, Sheet con filas, Escenario 2, correo con PDF
- Link compartido a carpeta "Proyecto de Instrucción"
- Tabla de parámetros actualizada con sección Make

### Próxima clase: Gemini API + 2 flujos
