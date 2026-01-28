# Clase 02: El Arte del Prompt

Presentación reveal.js para la segunda clase de AI 101.

---

<!-- .slide: data-background="#1a1a2e" -->

# El Arte del Prompt

### AI 101 - Clase 2

*Entertech School*

---

## Recap: Clase 01

Construiste tu **primer sistema** con Claude

```
SISTEMA = ROL + CONTEXTO + INSTRUCCIÓN
```

¿Cuántos lo usaron esta semana?

---

## Hoy

De resultados **pobres** a **extraordinarios**

- Con la misma herramienta

> "La IA no me da buenos resultados"

- ¿Seguro que el problema es la IA?

---

## Veamos

### El mismo pedido, 3 niveles

## Nivel 1: El Prompt Casual

```
Escribe un email de seguimiento
después de una reunión.
```

### Resultado Nivel 1

*[Demo en vivo con Claude]*

> ¿Lo enviarías tal cual?

---

## Nivel 2: Con Estructura

```
Actúa como un profesional de negocios.
Trabajo en una agencia de marketing y tuve
una reunión con un cliente potencial.
Escribe un email de seguimiento post-reunión.
Preséntalo como email listo para enviar.
```

### Resultado Nivel 2

*[Demo en vivo con Claude]*

> Mejor... pero ¿es TU tono?

---

## Nivel 3: RICE Completo

```
[ROL] Consultor senior de marketing
[INSTRUCCIÓN] Email de seguimiento 24h post-meeting
[CONTEXTO] Cliente: Dir. Marketing tech, pain points...
[EJEMPLO] Tono deseado + anti-ejemplos
```

### Resultado Nivel 3

*[Demo en vivo con Claude]*

> **Esto sí lo uso**

---

<!-- .slide: data-background="#16213e" -->

## El Framework

# RICE

---

## RICE

| Letra | Significado |
|-------|-------------|
| **R** | Rol |
| **I** | Instrucción |
| **C** | Contexto |
| **E** | Ejemplo |

---

## R = Rol

¿Quién quieres que sea la IA?

```
Eres un consultor senior de marketing
con 10 años de experiencia cerrando
clientes corporativos.
```

No: "Actúa como experto"
Sí: "Eres X con Y experiencia en Z"

---

## I = Instrucción

¿Qué debe hacer **exactamente**?

```
Escribe un email de seguimiento para
enviar 24 horas después de una reunión
de discovery con un cliente potencial.
```

Específica > Vaga

---

## C = Contexto

¿Qué información necesita?

```
- Cliente: Director de Marketing, empresa tech
- Reunión: Discovery de 45 min sobre rebranding
- Pain points: marca desactualizada
- Próximo paso: enviar propuesta en 1 semana
```

Más contexto = Menos adivinanza

---

## E = Ejemplo

¿Cómo debe verse el resultado?

```
[EJEMPLO de tono deseado]
"Gracias por compartir los desafíos..."

[ANTI-EJEMPLO - NO quiero esto]
- Nada genérico tipo "fue un placer"
- Nada vendedor tipo "no pierda esta oportunidad"
```

---

## El Secreto

El **Ejemplo** elimina ambigüedad

> Mostrar > Describir

---

## Evolución desde Clase 01

```
Clase 01          →  Clase 02
─────────────────────────────
ROL               →  R (Rol)
TAREA             →  I (Instrucción)
CONTEXTO          →  C (Contexto)
FORMATO           →  E (Ejemplo) ✨
```

El Ejemplo es el upgrade

---

<!-- .slide: data-background="#0f3460" -->

## Técnicas Avanzadas

---

## Chain of Thought

Pide a la IA que **piense paso a paso**

```
Antes de dar tu conclusión:
1. Primero identifica los factores clave
2. Luego evalúa pros y contras
3. Considera los riesgos
4. Finalmente, concluye con recomendación
```

---

## ¿Cuándo usar CoT?

- Análisis complejos
- Decisiones con múltiples factores
- Cuando necesitas ver el razonamiento
- Problemas matemáticos o lógicos

---

## Few-shot

Enseña con **ejemplos de input/output**

```
[EJEMPLOS]

Input: "El proyecto va bien"
Output: "✅ Proyecto en track"

Input: "Hay algunos retrasos menores"
Output: "⚠️ Proyecto con alertas"

Ahora genera para:
Input: [tu texto]
```

---

## ¿Cuándo usar Few-shot?

- Formatos específicos y consistentes
- Clasificaciones o categorizaciones
- Cuando el ejemplo habla más que la instrucción
- Templates reusables

---

<!-- .slide: data-background="#e74c3c" -->

## Anti-Hype

### Prompts que Fallan

---

## Mito 1

> "Existe el prompt perfecto"

**Realidad:** La iteración es parte del proceso

El primer intento casi nunca es el mejor

---

## Mito 2

> "Más largo = Mejor"

**Realidad:** Claridad > Longitud

Un prompt de 50 palabras claras
supera uno de 200 confusas

---

## Mito 3

> "Copy-paste de internet funciona"

**Realidad:** Requiere adaptación

Los prompts son contextuales

Tu situación ≠ La del tutorial

---

## Mito 4

> "La IA entiende implícitos"

**Realidad:** Explícito siempre gana

Lo que no dices, la IA lo inventa

---

## Prompts que Fallan

### 1. Rol sin contexto

```
❌ Eres un experto. Analiza esto.
```

¿Experto en qué? ¿Analizar cómo?

---

## Prompts que Fallan

### 2. Instrucciones contradictorias

```
❌ Sé breve pero detallado.
   Dame un resumen completo.
   Máximo 100 palabras pero no omitas nada.
```

---

## Prompts que Fallan

### 3. Pedir datos específicos

```
❌ ¿Cuál es el precio actual de Bitcoin?
❌ ¿Cuántos empleados tiene Apple en 2025?
```

La IA puede inventar datos que no tiene

**Siempre verifica datos factuales**

---

## La Regla de Oro

> "Si tu prompt requiere que la IA adivine,
> probablemente vas a iterar mucho"

---

<!-- .slide: data-background="#1a1a2e" -->

## Lab Time

---

## Prompt Battle

**Mismo reto, diferentes soluciones**

1. Todos escriben su mejor prompt
2. Ejecutan en Claude
3. Votamos el mejor resultado
4. Discutimos qué funcionó

---

## El Reto

> Tu jefe te pide que resumas un documento
> técnico de 10 páginas para el CEO.
>
> El CEO odia el tecnicismo y quiere saber:
> ¿qué significa esto para el negocio?

**8 minutos para tu prompt**

---

## Lab: Tus 3 Prompts Maestros

1. **Prompt de transformación** (del Battle)
2. **Prompt de análisis** (RICE + Chain of Thought)
3. **Prompt reusable** (RICE + Few-shot)

Documentados y listos para reusar

---

## Formato de Documentación

```
PROMPT MAESTRO: [Nombre]
Uso: [Para qué sirve]
Técnicas: RICE + [otras]
---
[Prompt completo]
---
Screenshot del resultado
```

---

## Tips para el Lab

| Tip | Ejemplo |
|-----|---------|
| Incluye anti-ejemplos | "NO quiero que sea vendedor" |
| Usa CoT para análisis | "Primero identifica, luego evalúa..." |
| Usa Few-shot para formatos | 2-3 ejemplos de input/output |
| Itera sin miedo | El primer draft no es el final |

---

## Showcase

### Compartan su mejor prompt

- ¿Qué técnicas usaste?
- ¿Cuántas iteraciones?
- ¿Lo usarías en tu trabajo?

---

## Entregable

### 3 Prompts Maestros

1. Prompt de transformación + screenshot
2. Prompt de análisis (CoT) + screenshot
3. Prompt reusable (Few-shot) + screenshot

Documentados en formato especificado

---

## Preview: Clase 3

### Tu Copiloto de Contenido

De prompts a **flujos de trabajo completos**

Crearás contenido profesional publicable

---

<!-- .slide: data-background="#1a1a2e" -->

## Frase de Cierre

> "Un prompt genérico produce resultados genéricos.
> Un prompt diseñado produce resultados extraordinarios."

---

## La Tarea de esta Semana

Cada vez que uses Claude:

1. Aplica RICE
2. Incluye al menos 1 ejemplo
3. Nota la diferencia

---

## Gracias

### Nos vemos en la Clase 3

*Entertech School*
