# Guía del Facilitador - Clase 02: El Arte del Prompt

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **RICE**: Framework de prompts — Rol, Instrucción, Contexto, Ejemplo.
- **Ejemplo**: Muestra de output deseado que elimina ambigüedad (mostrar > describir).
- **Chain of Thought**: Pedir razonamiento paso a paso antes de la conclusión.
- **Few-shot**: Enseñar con 2-3 ejemplos de input → output.
- **Iteración**: Refinar el prompt basado en resultados (normal, no falla).

---

## Analogías Útiles

**RICE como receta de cocina:**
Ingredientes (contexto), instrucciones (qué hacer), foto del plato terminado (ejemplo). Sin la foto, el chef interpreta.

**Ejemplo vs descripción:**
"Dame un email profesional" vs "Dame un email como este: [ejemplo]". El segundo elimina 90% de ambigüedad.

**Chain of Thought como "muestra tu trabajo":**
Como el profesor que pide ver el proceso, no solo la respuesta final. Reduce errores en análisis complejos.

**Few-shot como enseñar por imitación:**
Un niño aprende mejor viendo ejemplos que escuchando explicaciones. La IA también.

---

## Contexto Actual

### Productividad: Los datos reales

Estudios recientes muestran ganancias de productividad del 25-30% con IA bien aplicada, y hasta 56% más rápido en tareas de conocimiento. Pero solo 13% de trabajadores reciben entrenamiento formal en IA.

> **Para mencionar en clase:** "La IA puede darte 30% más productividad, pero el 87% no recibe entrenamiento. Este curso los pone en el 13% que sí sabe usarla."

**Fuentes:** [McKinsey State of AI](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai), [SurveyMonkey AI Report](https://www.surveymonkey.com/curiosity/ai-workplace-statistics/)

---

## Momentos Clave de la Clase

### Pregunta Detonadora

**Respuesta correcta:** C - Los ejemplos de output deseado

**Por qué las otras NO:**
| Opción | Por qué NO |
|--------|-----------|
| A | El rol ayuda, pero sin ejemplo el output sigue siendo genérico. |
| B | Más palabras sin dirección clara no mejoran nada. Calidad > cantidad. |
| D | Las primeras palabras importan poco si falta el ejemplo concreto. |

**Script post-votación:**
```
Facilitador: "¿Quién votó B, que es la longitud? ¿Por qué?"
[Escuchar respuestas]
Facilitador: "La respuesta es C. El ejemplo elimina ambigüedad — la IA VE qué quieres en vez de adivinar. Es la diferencia entre describir un plato y mostrar la foto."
```

**Tip:** Muchos votarán A (rol). Usar esto para mostrar la evolución de Clase 01 a 02.

---

### Demo Principal

**Qué mostrar:**
El mismo email de seguimiento post-reunión en 3 niveles: casual, estructurado (Clase 01), RICE completo.

**Script sugerido:**
```
Facilitador: "Voy a mostrarles el mismo pedido, 3 formas diferentes..."
[Nivel 1 - casual]
Facilitador: "¿Enviarían esto a un cliente? Genérico, ¿verdad?"
[Nivel 2 - con estructura]
Facilitador: "Mejor. Pero ¿es SU tono? ¿Su estilo?"
[Nivel 3 - RICE con ejemplo]
Facilitador: "¿Qué cambió? El ejemplo le mostró exactamente cómo debe verse."
```

**Si algo sale mal:**
Si el Nivel 3 no es perfecto: "Aquí iteraríamos. Pero noten que ya estamos 80% ahí vs 40% del Nivel 1."

### Transición al Lab

**Script sugerido:**
```
Facilitador: "Ahora ustedes van a construir RICE para su tarea real. Empiecen por el Ejemplo — definan cómo debe verse el output."
Facilitador: "Levanten la mano cuando tengan los 4 componentes escritos."
```

---

## Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Mi prompt es muy largo" | Confunde longitud con calidad | "¿Tienes ejemplo? Eso importa más que las palabras" |
| Prompt sin ejemplo | No internalizó el upgrade de hoy | "¿Cómo se ve un buen resultado para ti? Escríbelo" |
| Confusión CoT vs Few-shot | Normal en primera exposición | "CoT para pensar, Few-shot para formatear" |
| Battle sin energía | Falta competitividad | "¿Quién cree que puede ganar? Demuéstrenlo" |

---

## Preguntas Frecuentes

### "¿Siempre tengo que usar RICE completo?"
No para todo. Tareas simples no lo necesitan. Pero cuando algo no funciona, RICE es tu checklist de diagnóstico.

### "¿Cuántos ejemplos en Few-shot?"
2-3 suelen ser suficientes. Más de 5 puede confundir a la IA.

### "¿Puedo mezclar CoT y Few-shot?"
Sí, pero con cuidado. Prompts muy largos diluyen el foco. Prueba qué funciona para tu caso.

### "¿Esto funciona en ChatGPT?"
Sí. RICE y estas técnicas funcionan en cualquier LLM. Los principios son universales.

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~10 | Recap + hook | Pregunta sobre uso de sistema semana pasada |
| ~30 | Demo 3 niveles | Comentarios sobre diferencia del ejemplo |
| ~55 | RICE construido | Manos arriba: "¿Quién tiene los 4 componentes?" |
| ~65 | Primer prompt probado | Pasear, verificar ejecución |
| ~105 | Battle completado | Votación realizada, ganador anunciado |
| ~130 | Segundo prompt listo | Screenshots de ambos prompts |
| ~150 | Cierre | 2-3 compartieron, entregable claro |

---

## Tips de Facilitación

### Si el grupo está callado:
- En el Battle, nombrar a alguien: "Carlos, ¿qué enfoque usaste? Compártenos"
- Modelar primero mostrando tu propio prompt

### Si alguien domina la conversación:
- "Guardemos las técnicas avanzadas para después. Primero aseguremos que todos tienen RICE."

### Si hay resistencia a la IA:
- "El objetivo no es depender de IA, sino tener otra herramienta en tu arsenal"
- Mostrar caso donde IA falló y el juicio humano fue necesario

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase vamos a pasar de prompts individuales a flujos de trabajo completos. Los prompts RICE que crearon hoy se convierten en bloques para crear contenido profesional publicable."

**Tarea para mencionar:**
2 prompts maestros documentados — uno RICE básico, uno con técnica avanzada (CoT o Few-shot). Google Doc con screenshots.
