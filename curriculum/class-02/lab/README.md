# Lab 02: Mis Prompts Maestros

Construirás 2 prompts maestros usando RICE y técnicas avanzadas, listos para reusar en tu trabajo. Al terminar, tendrás prompts documentados que transforman tareas recurrentes en resultados consistentes.

> ⏱️ **Tiempo total:** 60 minutos

### 🎯 Objetivo

Crear 2 prompts maestros documentados: uno con RICE básico y otro con técnica avanzada (CoT o Few-shot).

---

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Claude abierto | Tab lista para prompts |
| 3 tareas reales | De tu trabajo actual |
| Entregable Clase 01 | Tu sistema revisor (o similar) |
| Google Doc | Listo para documentar |

---

## Parte 1: Construye RICE con TU Tarea (20 min)

Construye tu primer prompt RICE usando una de las 3 tareas reales que trajiste.

### 1.1. R = Rol (2 min)

```
Eres un _______________ con experiencia en _______________.
```

### 1.2. I = Instrucción (2 min)

¿Qué debe hacer EXACTAMENTE? Verbo de acción + qué + para qué.

```
[Verbo] _______________________________________________
```

### 1.3. C = Contexto (3 min)

```
- Audiencia: _______________
- Situación: _______________
- Restricciones: _______________
```

### 1.4. E = Ejemplo (5 min)

**Output deseado:** `"[Fragmento de cómo debe verse]"`

**Anti-ejemplos:**
- NO quiero que sea ___
- NO quiero que suene ___

### 1.5. Ensambla y prueba (8 min)

```
[ROL]
Eres un [tu rol] con experiencia en [tu área].

[INSTRUCCIÓN]
[Tu instrucción específica]

[CONTEXTO]
- [Tus bullets de contexto]

[EJEMPLO de output deseado]
"[Tu ejemplo]"

[ANTI-EJEMPLO]
- [Tus anti-ejemplos]
```

Ejecuta en Claude. ¿Es útil? Itera si es necesario.

✅ **Checkpoint:** Tienes prompt RICE ensamblado, probado en Claude, y al menos 1 iteración de mejora.

---

## Parte 2: Prompt Battle (20 min)

**Escenario:**
> Tu jefe te pide que resumas un documento técnico de 10 páginas para el CEO en 2 minutos. El CEO odia el tecnicismo y quiere saber: ¿qué significa esto para el negocio?

### Ejecución

1. **Escribe tu prompt** usando RICE (8 min)
2. **Ejecuta y captura** screenshot (2 min)
3. **Votación** — 3-4 voluntarios comparten, votamos el mejor (10 min)

✅ **Checkpoint:** Tienes prompt para el reto del CEO, ejecutado, y screenshot capturado.

---

## Parte 3: Técnica Avanzada (15 min)

Elige UNA técnica para tu segundo prompt maestro.

### Opción A: Chain of Thought

Para análisis y decisiones. Pide razonar paso a paso.

```
[ROL] Eres un [experto] en [industria].

[INSTRUCCIÓN]
Analiza [qué] y dame [resultado].

Antes de concluir, piensa paso a paso:
1. Identifica [aspecto 1]
2. Evalúa [aspecto 2]
3. Concluye con [recomendación]

[CONTEXTO]
- Situación: ___
- Objetivo: ___

[EJEMPLO]
"1. Hallazgo: ... 2. Implicación: ... 3. Recomendación: ..."
```

### Opción B: Few-shot

Para formatos consistentes. Enseña con ejemplos.

```
[ROL] Eres [rol] en [área].

[INSTRUCCIÓN]
Genera [qué] siguiendo el formato de los ejemplos.

[CONTEXTO]
- Audiencia: ___ / Tono: ___

[EJEMPLOS]
Input: [ejemplo 1] → Output: [resultado exacto]
Input: [ejemplo 2] → Output: [mismo formato]

Ahora genera para:
Input: [tu input real]
```

**Crea, ejecuta y captura screenshot** (15 min)

✅ **Checkpoint:** Tienes segundo prompt con técnica avanzada (CoT o Few-shot), ejecutado, y screenshot capturado.

---

## 📝 Entregable

**2 prompts maestros en Google Doc:**

### Prompt 1: RICE (de Parte 1 o Battle)
```
PROMPT MAESTRO: [Nombre]
Uso: [Para qué]
---
[Prompt completo]
---
Screenshot
```

### Prompt 2: Técnica Avanzada (de Parte 3)
```
PROMPT MAESTRO: [Nombre]
Técnicas: RICE + [CoT o Few-shot]
---
[Prompt completo]
---
Screenshot
```

**Entrega:** Link público del Google Doc.

---

## Checklist

- [ ] ¿Cada prompt tiene los 4 elementos de RICE?
- [ ] ¿Incluí ejemplo de output deseado?
- [ ] ¿Son para tareas REALES de mi trabajo?
- [ ] ¿Los screenshots muestran resultados útiles?

---

## 💭 Reflexión

Antes de entregar, responde mentalmente:

1. ¿Cuál de los 4 elementos de RICE fue más difícil de definir? ¿Por qué?
2. ¿El Ejemplo cambió significativamente la calidad del output?
3. ¿Qué prompt de tu semana pasada mejoraría más con RICE?
