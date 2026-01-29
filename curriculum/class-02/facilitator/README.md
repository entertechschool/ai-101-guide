# Guía del Facilitador - Clase 02: El Arte del Prompt

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **RICE**: Framework de prompts — Rol, Instrucción, Contexto, Ejemplo.
- **Ejemplo**: Muestra de output deseado que elimina ambigüedad (mostrar > describir).
- **Few-shot**: Enseñar con 2-3 ejemplos de input → output.
- **Triage**: Clasificar y priorizar mensajes según urgencia e impacto.
- **Iteración progresiva**: Agregar técnicas una a una para ver el impacto.

---

## Analogías Útiles

**RICE como receta de cocina:**
Ingredientes (contexto), instrucciones (qué hacer), foto del plato terminado (ejemplo). Sin la foto, el chef interpreta.

**Ejemplo vs descripción:**
"Dame una tabla de clasificación" vs "Dame una tabla como esta: [ejemplo]". El segundo elimina 90% de ambigüedad.

**Triage como urgencias de hospital:**
No atiendes por orden de llegada — priorizas por gravedad. La IA puede ayudar a clasificar, pero el juicio final es humano.

**Few-shot como enseñar por imitación:**
Un niño aprende mejor viendo ejemplos que escuchando explicaciones. La IA también.

---

## Contexto Actual

### Por qué triage y no email genérico

El ejercicio anterior (email de seguimiento) era abstracto y difícil de comparar entre estudiantes. El triage de mensajes:
- Es universal (todos han recibido mensajes de clientes o equivalentes)
- Tiene output verificable (tabla con campos fijos)
- Permite comparación objetiva entre iteraciones
- Introduce las limitaciones de forma natural

### El caso PetShop Express

Elegimos productos para mascotas porque:
- Producto simple y universal
- Genera variedad natural de mensajes (urgencia médica, quejas, consultas)
- No requiere conocimiento técnico específico
- Los mensajes mockup cubren casos límite interesantes

---

## Los 5 Mensajes y Por Qué Cada Uno

| # | Mensaje | Por qué lo incluimos |
|---|---------|----------------------|
| 1 | Pedido retrasado + perro con dieta especial | Urgencia REAL (médica) pero tono calmado |
| 2 | Consulta de producto visto en IG | Categoría ambigua: ¿venta o soporte? |
| 3 | Cliente enojado pidiendo reembolso | Tono urgente pero ¿es la mayor prioridad? |
| 4 | Corrección de factura "no urgente" | Dice "no urgente" pero tiene deadline real |
| 5 | Vitaminas que "no funcionaron" | Múltiples categorías posibles |

### Errores esperados de la IA

**Mensaje 1 vs 3:** La IA puede priorizar el mensaje 3 por el tono agresivo, cuando el mensaje 1 tiene urgencia real (salud del animal).

**Mensaje 4:** La IA puede respetar "no urgente" ignorando el deadline del viernes.

**Mensaje 2 y 5:** Categorías ambiguas que la IA asignará de forma inconsistente.

---

## Momentos Clave de la Clase

### Pregunta Detonadora

**Respuesta correcta:** C - Los ejemplos de output deseado

**Por qué las otras NO:**
| Opción | Por qué NO |
|--------|-----------|
| A | El rol ayuda con criterio, pero sin ejemplo el formato es inconsistente. |
| B | Más palabras sin dirección clara no mejoran nada. Calidad > cantidad. |
| D | Las primeras palabras importan poco si falta el ejemplo concreto. |

**Script post-votación:**
```
Facilitador: "¿Quién votó A, que es el rol? ¿Por qué?"
[Escuchar respuestas]
Facilitador: "El rol SÍ ayuda — lo veremos en el lab. Pero la respuesta es C.
Los ejemplos calibran el criterio Y el formato. Mostrar > describir."
```

---

### Demo Principal: Triage en 3 Niveles

**Preparación:** Ten los 5 mensajes de PetShop Express listos. Ejecuta los 3 niveles ANTES de clase para tener los resultados.

**Qué mostrar:**
1. Nivel 1 (casual): Resultado caótico, formatos diferentes
2. Nivel 2 (con rol): Mejor criterio, formato aún inconsistente
3. Nivel 3 (RICE completo): Tabla consistente con prioridades calibradas

**Script sugerido:**
```
Facilitador: "Tengo 5 mensajes de clientes. ¿Cuál atiendo primero?"
[Nivel 1]
Facilitador: "Miren el resultado. ¿Pueden comparar fácilmente? ¿Saben qué hacer?"
[Nivel 2]
Facilitador: "Mejor criterio. Pero ¿el formato es consistente?"
[Nivel 3]
Facilitador: "Ahora sí. Tabla, emojis de prioridad, acción siguiente clara.
¿Qué cambió? Los EJEMPLOS le mostraron exactamente cómo clasificar."
```

**Si algo sale mal:**
Si el Nivel 3 tiene errores visibles: "Perfecto — miren este error. [Señalar]. La IA clasificó [X] como [Y] cuando debería ser [Z]. Esto es NORMAL. Por eso el análisis crítico es parte del lab."

---

### Transición al Lab

**Script sugerido:**
```
Facilitador: "Ahora ustedes van a construir esto paso a paso.
Parte 1: Sin técnicas — vean el caos.
Parte 2: Agregan rol — vean qué mejora.
Parte 3: Agregan formato — vean la consistencia.
Parte 4: Agregan ejemplos — vean la calibración.
Parte 5: Encuentren los errores — porque SÍ habrá errores."
```

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Mi prompt es muy largo" | Confunde longitud con calidad | "¿Tienes ejemplos? Eso importa más que las palabras" |
| Solo documenta versión final | No comparó la evolución | "Vuelve a correr las 4 versiones y compara" |
| No encuentra errores | Confía ciegamente en la IA | "Compara mensaje 1 vs 3. ¿Cuál priorizó? ¿Es correcto?" |
| Categorías inventadas | No siguió las restricciones | "Las categorías son fijas: Envío, Producto, Facturación, Venta, Queja" |

---

## Preguntas Frecuentes

### "¿Siempre tengo que usar RICE completo?"
No para todo. Tareas simples no lo necesitan. Pero cuando algo no funciona, RICE es tu checklist de diagnóstico.

### "¿Cuántos ejemplos en Few-shot?"
2-3 suelen ser suficientes. Más de 5 puede confundir a la IA.

### "¿Por qué la IA se equivoca en las prioridades?"
Porque no tiene contexto completo. El mensaje 4 dice "no urgente" — la IA lo cree. Tú sabes que hay deadline. Ese juicio es humano.

### "¿Esto funciona en ChatGPT?"
Sí. RICE y estas técnicas funcionan en cualquier LLM. Los principios son universales.

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~10 | Recap + hook | Pregunta sobre uso de sistema semana pasada |
| ~25 | Demo 3 niveles | Comentarios sobre diferencia del ejemplo |
| ~35 | Parte 1-2 completada | "¿Quién tiene las 2 primeras versiones?" |
| ~55 | Parte 3 completada | "¿Quién tiene tabla con formato?" |
| ~75 | Parte 4 completada | "¿Quién tiene los 5 mensajes clasificados?" |
| ~85 | Análisis crítico | "¿Quién encontró un error? Compártanlo" |
| ~95 | Cierre | Entregable claro, preview clase 03 |

---

## Sección Anti-Hype: Cómo Manejarla

Esta clase tiene una sección explícita de limitaciones. Es intencional.

**Script para introducir limitaciones:**
```
Facilitador: "La IA NO es perfecta. Vamos a ver 3 errores comunes.
Esto no es para asustarlos — es para que sepan cuándo confiar y cuándo verificar."
```

**Los 3 errores a destacar:**
1. **Prioridad por tono vs realidad:** Mensaje 3 suena urgente pero mensaje 1 tiene urgencia médica real
2. **Respetar lo que el cliente DICE:** Mensaje 4 dice "no urgente" pero tiene deadline
3. **Categorías ambiguas:** Mensaje 5 puede ser Producto, Queja, o Venta

**Script para cerrar:**
```
Facilitador: "La IA clasifica. Tú validas. Esa combinación es más poderosa
que cualquiera de los dos solos."
```

---

## Tips de Facilitación

### Si el grupo está callado:
- En el análisis crítico, nombrar a alguien: "María, ¿qué error encontraste en mensaje 1?"
- Compartir tu propio error primero: "Yo vi que la IA priorizó mensaje 3 sobre mensaje 1. ¿A ustedes les pasó?"

### Si alguien domina la conversación:
- "Guardemos las técnicas avanzadas. ¿Alguien más encontró un error diferente?"

### Si hay frustración con errores de la IA:
- "Exacto. Por eso el análisis crítico es parte del entregable. No es bug — es feature."

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "Hoy construyeron UN prompt maestro para clasificar mensajes.
> La próxima clase vamos a encadenar múltiples prompts para crear
> contenido profesional publicable — de idea a pieza final."

**Tarea para mencionar:**
Google Doc con: 4 versiones del prompt, tabla de 5 mensajes, reflexión crítica con 1 error.
