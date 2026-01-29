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

### Fase 1: Recap + Hook (10 min)
**Checkpoint:** min 0-10

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
**Checkpoint:** min 10-30

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

4. **Transición a RICE** (4 min)
   - "¿Qué elemento hizo la mayor diferencia?"
   - Guiar hacia: "El ejemplo elimina ambigüedad"
   - Presentar RICE en 1 slide (tabla resumen)

**Frase clave:** "Mostrar es más poderoso que describir"

**Técnica de demo:**
- NO uses prompts pre-generados que parezcan trucados
- Acepta si hay un resultado imperfecto: "Iteraríamos aquí"
- La autenticidad genera más credibilidad

---

### Fase 3: Construir RICE con Práctica Inmediata (25 min)
**Checkpoint:** min 30-55

**Objetivo:** Que construyan RICE MIENTRAS aprenden, no después

> ⚠️ **CAMBIO CLAVE:** En lugar de 15 min de teoría pura, intercalamos explicación con micro-prácticas. Cada componente se explica Y se escribe inmediatamente.

**Hacer:**

1. **R = Rol** (5 min)
   - Explicar: "No es solo 'eres experto', es 'eres X con Y experiencia en Z'" (2 min)
   - **MICRO-PRÁCTICA:** "Escribe el ROL para TU tarea" (3 min)
   - Pedir 1-2 ejemplos en voz alta

2. **I = Instrucción** (5 min)
   - Explicar: "Específica > Vaga. Verbo de acción." (2 min)
   - **MICRO-PRÁCTICA:** "Escribe la INSTRUCCIÓN para tu tarea" (3 min)

3. **C = Contexto** (5 min)
   - Explicar: "Todo lo que la IA necesita para no adivinar" (2 min)
   - **MICRO-PRÁCTICA:** "Escribe 3 bullets de CONTEXTO" (3 min)

4. **E = Ejemplo** (10 min) — ÉNFASIS AQUÍ
   - Explicar: "El upgrade. Muestra qué SÍ quieres Y qué NO quieres" (4 min)
   - **MICRO-PRÁCTICA:** "Escribe 1 ejemplo de output + 2 anti-ejemplos" (6 min)

**Al terminar:** Los estudiantes ya tienen un prompt RICE armado para su tarea real.

**Frase clave:** "FORMATO te dice cómo. EJEMPLO te muestra exactamente qué."

---

### Fase 4: Ensamblar y Probar (10 min)
**Checkpoint:** min 55-65

**Objetivo:** Que todos ejecuten su primer prompt RICE

**Hacer:**
1. "Junten los 4 componentes en un solo prompt" (2 min)
2. "Ejecuten en Claude" (5 min)
3. "¿Funcionó? ¿Qué ajustarían?" (3 min)

**Circulación rápida:**
| Señal | Qué hacer |
|-------|-----------|
| No ejecutó | "¿Cuál componente te falta?" |
| Resultado malo | "¿Incluiste ejemplo de output?" |
| Resultado bueno | "¿Lo usarías tal cual mañana?" |

---

### Fase 5: Anti-Hype + Técnicas Avanzadas (15 min)
**Checkpoint:** min 65-80

**Objetivo:** Bajar expectativas irreales, introducir CoT/Few-shot brevemente

> ⚠️ **CAMBIO:** Anti-hype ANTES de técnicas avanzadas para que no piensen que "hay un truco mágico"

**Hacer:**

1. **Mitos a destruir** (5 min) - 1 SLIDE con tabla
   - "¿Cuál de estos han cometido?" (interacción)
   - Prompts que fallan: 1 slide con 3 ejemplos malos

2. **Chain of Thought** (4 min)
   - "Pedir que piense paso a paso ANTES de concluir"
   - Cuándo usarlo: análisis complejos, decisiones
   - NO demo larga - solo concepto

3. **Few-shot** (4 min)
   - "Enseñar con ejemplos de input → output"
   - Cuándo usarlo: formatos específicos, consistencia
   - NO demo larga - solo concepto

4. **Cierre de sección** (2 min)
   - "CoT para pensar. Few-shot para formatear."
   - "En el lab van a elegir UNA para su segundo prompt"

**Frase clave:** "Si tu prompt requiere que la IA adivine, vas a iterar mucho"

**Nota pedagógica:**
Estas técnicas se consolidan con uso, no con explicación.
El lab es donde las aplican.

---

### Fase 6: Prompt Battle (25 min)
**Checkpoint:** min 80-105

**Este es el momento de COMPETITIVE_COLLABORATION**

> ⚠️ **CAMBIO:** Battle ANTES del trabajo individual de técnicas avanzadas. Aprovecha la energía del grupo.

**Setup:**
- Anunciar el reto claramente
- Timer visible: 8 min para escribir
- Todos trabajan en silencio

**Ejecución:**
- 8 min: Escriben su prompt
- 2 min: Ejecutan y capturan
- 15 min: 3-4 voluntarios comparten, votación, discusión

**Facilitación del Battle:**
- Pedir voluntarios diversos (diferentes industrias/roles)
- Votar con manos levantadas o reacciones de chat
- Preguntar al ganador: "¿Qué incluiste que otros no?"
- Preguntar a quien no ganó: "¿Qué cambiarías ahora que viste otros?"

**Señales de éxito del Battle:**
- Energía competitiva pero respetuosa
- Sorpresa al ver enfoques diferentes
- "Ah, no pensé en incluir eso"

---

### Fase 7: Lab - Técnica Avanzada (25 min)
**Checkpoint:** min 105-130

**Objetivo:** Crear el segundo prompt maestro con CoT o Few-shot

**Hacer:**
1. Presentar las 2 opciones claramente (2 min)
   - Chain of Thought: para análisis
   - Few-shot: para formatos

2. "Elige UNA según tu necesidad" (1 min)

3. Trabajo individual (15 min)
   - Crear prompt con técnica elegida
   - Ejecutar y refinar

4. Captura y documentación (7 min)
   - Screenshot del prompt + resultado
   - Guardar en formato de entregable

**Circulación durante el lab:**

| Señal | Qué hacer |
|-------|-----------|
| Confusión CoT vs Few-shot | "¿Tu tarea es análisis o formato?" |
| Prompt muy largo | "CoT son pasos, no un ensayo" |
| Few-shot sin ejemplos | "¿Cuáles son 2 ejemplos de input/output?" |
| Terminó rápido | "¿Probaste ejecutarlo? ¿Funciona?" |

---

### Fase 8: Showcase + Cierre (20 min)
**Checkpoint:** min 130-150

**Objetivo:** Celebrar, consolidar, anticipar

**Hacer:**
1. **Showcase** (10 min)
   - 2-3 voluntarios muestran su mejor prompt
   - Enfocarse en: qué técnica usaron, qué aprendieron

2. **Consolidación** (5 min)
   - "RICE es su nueva base"
   - "CoT para análisis, Few-shot para formatos"
   - "El ejemplo es el diferenciador"

3. **Preview Clase 3** (3 min)
   - "De prompts a flujos de trabajo"
   - "Crearán contenido profesional publicable"
   - "Sus prompts de hoy serán herramientas para mañana"

4. **Entregable** (2 min)
   - Recordar: 2 prompts (no 3)
   - Formato simplificado
   - Google Doc con screenshots

**Frase de cierre:**
> "Un prompt genérico produce resultados genéricos. Un prompt diseñado produce resultados extraordinarios."

---

## Nuevo Flujo de Energía

```
min 0-10:   ████████░░ (Recap + Hook - OK)
min 10-30:  ██████████ (Demo transformación - PICO)
min 30-55:  ████████░░ (RICE con práctica - ACTIVO)
min 55-65:  ███████░░░ (Ensamblar y probar - MEDIO)
min 65-80:  ██████░░░░ (Anti-hype + Técnicas - MEDIO-BAJO)
min 80-105: ██████████ (Prompt Battle - PICO)
min 105-130:███████░░░ (Lab individual - MEDIO)
min 130-150:████████░░ (Showcase + Cierre - OK)
```

**Mejora:** No hay 30 min de teoría consecutiva. Alternan activo/pasivo.

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
- 80%+ construyen un prompt RICE funcional durante la clase
- El Prompt Battle genera energía y aprendizaje
- Todos tienen 2 prompts documentados al final
- Los prompts son para tareas REALES de su trabajo

**Alerta si:**
- Siguen haciendo prompts sin ejemplo
- No participan en el Battle (apatía)
- No trajeron tareas reales (hacen ejemplos genéricos)

---

## Errores Comunes del Facilitador

| Error | Corrección |
|-------|------------|
| Explicar RICE sin práctica | Micro-práctica después de cada letra |
| Battle sin energía | Aumentar competitividad "¿Quién cree que puede ganar?" |
| Saltarse el anti-hype | Es obligatorio, previene frustraciones futuras |
| Dar demasiado tiempo para 3 prompts | Ahora son 2, tiempo suficiente |
| Explicar CoT/Few-shot en profundidad | Solo concepto, el lab es donde practican |

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
