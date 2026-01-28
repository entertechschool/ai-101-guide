# Guía del Facilitador: El Arte del Prompt

> **Tiempo real de instrucción:** ~150 min (los 30 min restantes son buffer para breaks y troubleshooting)

---

## Preparación Previa

### Materiales necesarios
- [ ] Slides cargados y probados
- [ ] Demo de 3 niveles lista (email de seguimiento post-reunión)
- [ ] Texto técnico de prueba para el Prompt Battle (algo de 1-2 páginas)
- [ ] Claude abierto en una ventana separada
- [ ] Ejemplos de prompts que fallan preparados

### Ambiente
- [ ] Pantalla compartida configurada
- [ ] Timer visible para el Prompt Battle
- [ ] Sistema de votación listo (manos levantadas o chat)

### Contexto de la clase anterior
Los estudiantes llegan con:
- Experiencia usando Claude (al menos 1 semana)
- Conocimiento de estructura [ROL][CONTEXTO][TAREA][FORMATO]
- Un sistema básico creado (el revisor de comunicaciones)
- Expectativas de "siguiente nivel"

---

## Estructura con Checkpoints (~150 min)

### Fase 1: Recap + Hook (15 min)
**Checkpoint:** min 0-15

**Objetivo:** Reconectar con Clase 01, crear expectativa

**Hacer:**
1. Pregunta rápida: "¿Cuántos usaron su sistema de la semana pasada?"
2. Si hubo uso: "¿Funcionó? ¿Qué ajustaron?"
3. Si no hubo uso: "Hoy van a crear algo que SÍ van a usar"
4. Hook: "Hoy aprenden la diferencia entre buenos y extraordinarios"

**Frase clave:** "El problema no es la IA. Es cómo le hablamos."

**Evitar:**
- Recap largo de Clase 01
- Criticar si no usaron el sistema

---

### Fase 2: Demo de Transformación (20 min)
**Checkpoint:** min 15-35

**Objetivo:** Demostrar visualmente el poder de un buen prompt

**Hacer:**
1. **Nivel 1 - Casual** (3 min)
   - Prompt: "Escribe un email de seguimiento después de una reunión"
   - Ejecutar en vivo, mostrar resultado genérico
   - Preguntar: "¿Enviarían esto?"

2. **Nivel 2 - Estructura básica** (3 min)
   - Agregar ROL, CONTEXTO, TAREA, FORMATO
   - Ejecutar, mostrar mejora
   - Preguntar: "Mejor... pero ¿es SU tono?"

3. **Nivel 3 - RICE completo** (5 min)
   - Mostrar el prompt con Ejemplo y Anti-ejemplo
   - Ejecutar, mostrar resultado personalizado
   - Pausa. Dejar que comparen.

4. **Reflexión guiada** (4 min)
   - "¿Qué elemento hizo la mayor diferencia?"
   - Guiar hacia: "El ejemplo elimina ambigüedad"

**Frase clave:** "Mostrar es más poderoso que describir"

**Técnica de demo:**
- NO uses prompts pre-generados que parezcan trucados
- Acepta si hay un resultado imperfecto: "Iteraríamos aquí"
- La autenticidad genera más credibilidad

---

### Fase 3: Framework RICE (15 min)
**Checkpoint:** min 35-50

**Objetivo:** Que memoricen y entiendan cada componente

**Hacer:**
1. **R = Rol** (3 min)
   - "No es solo 'eres experto', es 'eres X con Y experiencia en Z'"
   - Ejemplo vs contraejemplo rápido

2. **I = Instrucción** (3 min)
   - "Específica > Vaga"
   - "Qué debe hacer EXACTAMENTE"

3. **C = Contexto** (3 min)
   - "Todo lo que la IA necesita saber para no adivinar"
   - "Más contexto = Menos iteraciones"

4. **E = Ejemplo** (6 min) — ÉNFASIS AQUÍ
   - "El upgrade desde Clase 01"
   - Ejemplo de output deseado
   - Anti-ejemplo de lo que NO quieres
   - "Esto elimina el 80% de la ambigüedad"

**Frase clave:** "FORMATO te dice cómo. EJEMPLO te muestra exactamente qué."

**Dinámica rápida:**
Pedir a 2-3 estudiantes que digan en voz alta:
- "R de..." → "Rol"
- "I de..." → "Instrucción"
- "C de..." → "Contexto"
- "E de..." → "Ejemplo"

---

### Fase 4: Técnicas Avanzadas (15 min)
**Checkpoint:** min 50-65

**Objetivo:** Introducir Chain of Thought y Few-shot

**Hacer:**
1. **Chain of Thought** (7 min)
   - "Pedir que piense paso a paso ANTES de concluir"
   - Demo rápida: análisis de decisión con vs sin CoT
   - Cuándo usarlo: análisis complejos, decisiones, razonamiento

2. **Few-shot** (7 min)
   - "Enseñar con ejemplos de input → output"
   - Demo: clasificación con 2-3 ejemplos
   - Cuándo usarlo: formatos específicos, consistencia

**Frase clave:** "CoT para pensar. Few-shot para formatear."

**Nota pedagógica:**
No profundizar demasiado aquí. El lab es donde practican.
Estas técnicas se consolidan con uso, no con explicación.

---

### Fase 5: Anti-Hype - Prompts que Fallan (10 min)
**Checkpoint:** min 65-75

**Objetivo:** Prevenir errores comunes, bajar expectativas irreales

**Hacer:**
1. **Mitos a destruir** (5 min)
   - "Existe el prompt perfecto" → La iteración es el proceso
   - "Más largo = mejor" → Claridad > longitud
   - "Copy-paste de internet" → Requiere adaptación
   - "La IA entiende implícitos" → Explícito siempre gana

2. **Prompts que fallan** (5 min)
   - Rol sin contexto: "Eres experto. Analiza esto." → ¿Experto en qué?
   - Instrucciones contradictorias: "Sé breve pero detallado"
   - Pedir datos específicos: "¿Precio actual de Bitcoin?" → Puede inventar

**Frase clave:** "Si tu prompt requiere que la IA adivine, vas a iterar mucho"

**Momento importante:**
Este es el momento "anti-hype" obligatorio del principio ANTI_HYPE_ALWAYS.
No minimizarlo. Los estudiantes recordarán esto cuando fallen sus prompts.

---

### Fase 6: Lab con Checkpoints (60 min)
**Checkpoint:** min 75-135

**Estructura interna:**

#### Parte 1: Demo Guiada (15 min) - min 75-90
- Todos hacen los 3 niveles de prompt juntos
- Observan la transformación en su propia pantalla
- Reflexión rápida grupal al final

#### Parte 2: Prompt Battle (20 min) - min 90-110
**Este es el momento de COMPETITIVE_COLLABORATION**

**Setup:**
- Anunciar el reto claramente
- Timer visible: 8 min para escribir
- Todos trabajan en silencio

**Ejecución:**
- 8 min: Escriben su prompt
- 2 min: Ejecutan y capturan
- 10 min: 3-4 voluntarios comparten, votación, discusión

**Facilitación del Battle:**
- Pedir voluntarios diversos (diferentes industrias/roles)
- Votar con manos levantadas o reacciones de chat
- Preguntar al ganador: "¿Qué incluiste que otros no?"
- Preguntar a quien no ganó: "¿Qué cambiarías ahora que viste otros?"

**Señales de éxito del Battle:**
- Energía competitiva pero respetuosa
- Sorpresa al ver enfoques diferentes
- "Ah, no pensé en incluir eso"

#### Parte 3: Prompts Individuales (25 min) - min 110-135
- 15 min: Prompt de Análisis (RICE + CoT)
- 10 min: Prompt Reusable (RICE + Few-shot)

**Circulación durante el lab:**

| Señal | Qué hacer |
|-------|-----------|
| Mira pantalla sin escribir | "¿Cuál de tus 3 tareas elegiste?" |
| Prompt muy corto | "¿Incluiste un ejemplo de output?" |
| Frustración | "¿Qué parte de RICE te falta?" |
| Terminó rápido | "¿Probaste agregar anti-ejemplos?" |

---

### Fase 7: Showcase + Cierre (15 min)
**Checkpoint:** min 135-150

**Objetivo:** Celebrar, consolidar, anticipar

**Hacer:**
1. **Showcase** (8 min)
   - 2-3 voluntarios muestran su mejor prompt
   - Enfocarse en: qué técnica usaron, qué aprendieron

2. **Consolidación** (4 min)
   - "RICE es su nueva base"
   - "CoT para análisis, Few-shot para formatos"
   - "El ejemplo es el diferenciador"

3. **Preview Clase 3** (3 min)
   - "De prompts a flujos de trabajo"
   - "Crearán contenido profesional publicable"
   - "Sus prompts de hoy serán herramientas para mañana"

**Frase de cierre:**
> "Un prompt genérico produce resultados genéricos. Un prompt diseñado produce resultados extraordinarios."

---

## Conceptos Clave

| Término | Definición para explicar |
|---------|-------------------------|
| **RICE** | Framework: Rol, Instrucción, Contexto, Ejemplo |
| **Chain of Thought** | Pedir razonamiento paso a paso antes de la conclusión |
| **Few-shot** | Enseñar con ejemplos de input → output |
| **Anti-ejemplo** | Mostrar qué NO quieres para eliminar ambigüedad |
| **Iteración** | Refinar el prompt basado en resultados (normal, no falla) |

---

## Analogías Útiles

| Concepto | Analogía |
|----------|----------|
| RICE | Receta de cocina: ingredientes (contexto), instrucciones (qué hacer), foto del plato (ejemplo) |
| Ejemplo vs Formato | "Dame un email profesional" vs "Dame un email como este: [ejemplo]" |
| Chain of Thought | Profesor que pide "muestra tu trabajo" antes de la respuesta final |
| Few-shot | Enseñar a un niño por imitación, no por explicación |

---

## Señales de Éxito

**La clase funcionó si:**
- 80%+ entiende y aplica RICE en sus prompts
- El Prompt Battle genera energía y aprendizaje
- Preguntan sobre cuándo usar CoT vs Few-shot
- Sus prompts del lab son notablemente mejores que los de Clase 01

**Alerta si:**
- Siguen haciendo prompts sin ejemplo
- No participan en el Battle (apatía)
- Comentarios tipo "es mucho esfuerzo para un prompt"

---

## Errores Comunes del Facilitador

| Error | Corrección |
|-------|------------|
| Sobreexplicar las técnicas | Menos teoría, más práctica |
| Battle sin energía | Aumentar competitividad "¿Quién cree que puede ganar?" |
| Saltarse el anti-hype | Es obligatorio, previene frustraciones futuras |
| No dar suficiente tiempo para el lab | El lab ES la clase, la teoría es setup |

---

## Preguntas Frecuentes

**"¿Siempre tengo que usar RICE completo?"**
> No para todo. Tareas simples no lo necesitan. Pero cuando algo no funciona, RICE es tu checklist de diagnóstico.

**"¿Cuántos ejemplos debo poner en Few-shot?"**
> 2-3 suelen ser suficientes. Más de 5 empieza a ser contraproducente (la IA se confunde).

**"¿Puedo mezclar Chain of Thought y Few-shot?"**
> Sí, pero con cuidado. Los prompts muy largos pueden diluir el foco. Prueba y ve qué funciona mejor para tu caso específico.

**"¿Esto funciona igual en ChatGPT?"**
> Sí. RICE y estas técnicas funcionan en cualquier LLM. Los principios son universales.

---

## Conexión con Otras Clases

**Desde Clase 01:**
- Evolucionan de [ROL][CONTEXTO][TAREA][FORMATO] a RICE
- Sus sistemas básicos se vuelven sistemas profesionales
- La práctica con Claude se convierte en destreza

**Hacia Clase 03:**
- Los prompts de hoy se convierten en bloques para flujos de trabajo
- RICE aplicado a creación de contenido profesional
- De "un prompt" a "un proceso de producción"
