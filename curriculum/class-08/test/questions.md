# Test Módulo 2 - Questions

**8 preguntas diagnósticas**

---

## Preguntas 1-2 (Clase 05: Tu Primer Agente IA)

### Pregunta 1

¿Cuál es la diferencia principal entre una automatización y un agente IA?

- A) Un agente es más rápido que una automatización
- B) Un agente usa IA para tomar decisiones, no solo seguir reglas fijas
- C) Un agente puede conectar más herramientas que una automatización
- D) No hay diferencia real, son sinónimos

> Respuesta: B
> Justificación: La diferencia fundamental es que una automatización ejecuta reglas fijas (IF/THEN), mientras que un agente usa IA para DECIDIR. El agente analiza el contexto y toma decisiones variables — no sigue un camino predeterminado.

### Pregunta 2

¿Qué define la calidad de las decisiones de un agente IA?

- A) El modelo de IA que uses (Grok, GPT, Claude)
- B) La cantidad de módulos en Make
- C) El SystemPrompt con categorías y reglas claras
- D) La velocidad de respuesta del webhook

> Respuesta: C
> Justificación: El battle de C06 lo demostró: mismo modelo (Grok), mismos mensajes, resultados diferentes. La variable fue el SystemPrompt. Categorías claras + reglas específicas + formato de salida = decisiones de calidad.

---

## Preguntas 3-4 (Clase 06: Tu Agente Inteligente)

### Pregunta 3

¿Qué es un Router en Make y para qué sirve?

- A) Un módulo que acelera el procesamiento del flujo
- B) Un módulo que divide el flujo en rutas condicionales según Filters
- C) Un módulo que conecta Make con APIs externas
- D) Un módulo que registra datos en Google Sheets

> Respuesta: B
> Justificación: El Router evalúa condiciones (Filters) y dirige el flujo por rutas diferentes. Ejemplo: si la categoría es URGENTE → ruta 1, si es CONSULTA → ruta 2. Sin Router, todos los mensajes reciben la misma acción.

### Pregunta 4

¿Para qué sirve el logging con Google Sheets en un agente profesional?

- A) Para que el agente sea más rápido
- B) Para reemplazar el email como canal de notificación
- C) Para auditar las decisiones del agente y mejorar con datos reales
- D) Para compartir resultados automáticamente con el equipo

> Respuesta: C
> Justificación: Sin registro, no puedes saber si el agente clasifica bien o mal. Google Sheets como bitácora permite: ver todas las decisiones, identificar patrones de error, y mejorar el SystemPrompt con evidencia — no con intuición.

---

## Preguntas 5-6 (Clase 07: Mi Agente Real)

### Pregunta 5

Al transferir el agente de PetShop a tu caso real, ¿qué CAMBIA y qué se queda?

- A) Cambia todo — hay que construir desde cero
- B) Cambian el SystemPrompt, categorías, reglas y formulario. Se queda la arquitectura (Webhook → OpenRouter → Router → Gmail → Sheets)
- C) Solo cambia el nombre del escenario en Make
- D) Cambia la herramienta — se necesita otra plataforma diferente a Make

> Respuesta: B
> Justificación: La transferencia consiste en mantener la arquitectura probada y cambiar el "cerebro": SystemPrompt (nuevas reglas), categorías (nuevos Filters), formulario (nuevos campos) y emails (nuevos asuntos). La estructura de Make se clona y adapta.

### Pregunta 6

Tu agente clasifica todos los mensajes con la misma categoría. ¿Qué arreglas primero?

- A) Las reglas del SystemPrompt — probablemente no son suficientemente específicas
- B) El modelo de IA — necesitas uno más potente
- C) El Router — los Filters deben estar mal configurados
- D) El formulario — los campos no envían suficiente información

> Respuesta: A
> Justificación: Si el agente clasifica todo igual, el problema casi siempre está en el SystemPrompt: reglas vagas, categorías sin diferenciadores claros, o falta de ejemplos. El modelo y el Router solo ejecutan lo que el SystemPrompt define.

---

## Pregunta 7 (Integración M2)

### Pregunta 7

Un agente IA profesional completo necesita:

- A) Solo un buen modelo de IA y un SystemPrompt
- B) Formulario bonito + muchos módulos en Make
- C) Aprobación del equipo de TI para implementar
- D) Cerebro (SystemPrompt con reglas) + acciones diferenciadas (Router + Gmail) + logging (Sheets) + supervisión humana

> Respuesta: D
> Justificación: Un agente profesional tiene 4 componentes: (1) cerebro que decide bien (SystemPrompt), (2) acciones diferentes por categoría (Router + Gmail), (3) registro para auditar y mejorar (Sheets), y (4) supervisión — porque ningún agente reemplaza el criterio humano.

---

## Pregunta 8 (Autoevaluación)

### Pregunta 8

Después de completar el Módulo 2, ¿qué tan preparado/a te sientes para integrar un agente IA en tu trabajo real?

- A) Muy preparado/a — podría construir y adaptar agentes para diferentes procesos
- B) Bastante preparado/a — puedo hacerlo con algo de referencia al material del curso
- C) Algo inseguro/a — necesitaría más práctica antes de implementarlo en mi trabajo
- D) Muy inseguro/a — no sabría por dónde empezar sin guía paso a paso

> Sin respuesta correcta — todas las opciones son válidas para diagnóstico
> Justificación: Esta pregunta mide la autopercepción del estudiante. Cualquier respuesta es valiosa como dato para el facilitador y para el propio estudiante.
