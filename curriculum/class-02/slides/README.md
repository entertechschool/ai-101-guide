<!-- .slide: data-background="#0A192F" -->

# Clase 02: El Arte del Prompt
## De resultados mediocres a extraordinarios

*AI 101 - Entertech School*

---

## 🔗 Transición: Clase 01 → Clase 02

### La clase pasada:
- Construiste tu primer SISTEMA con Claude
- Fórmula: `ROL + CONTEXTO + INSTRUCCIÓN`

### Hoy:
- Evolucionamos a **RICE** (Rol, Instrucción, Contexto, Ejemplo)
- El Ejemplo es el upgrade que transforma resultados

> "La IA no me da buenos resultados" — ¿Seguro que el problema es la IA?

---

## ¿Por Qué Esto Importa?

### El problema:
El 95% escribe prompts como mensajes de texto: vagos, sin estructura

### La oportunidad:
Un prompt bien diseñado produce resultados que usas **tal cual**

> **Realidad:** La iteración es inevitable. Pero un buen prompt reduce de 10 iteraciones a 2.

---

## 🧠 Pregunta Detonadora

### ¿Cuál elemento de un prompt hace MÁS diferencia en la calidad del resultado?

**A)** El rol que le asignas a la IA

**B)** La longitud y detalle del prompt

**C)** Los ejemplos de output deseado

**D)** Las palabras que usas al inicio

> 🕐 30 segundos para pensar → levanten la mano

---

## 🎬 Demo: Triage de Mensajes — 3 Niveles

### El Caso: PetShop Express
Recibes 5 mensajes de clientes. ¿Cuál atender primero?

### Nivel 1: Prompt Casual
```
Clasifica estos mensajes de clientes.
```

### Nivel 2: Con Rol
```
Eres agente de soporte senior...
Clasifica estos mensajes.
```

### Nivel 3: RICE Completo
Con Rol + Formato de tabla + **Ejemplos de clasificación**

> 🎬 **Demo en vivo** - Veremos cómo evoluciona el resultado

---

## 🎯 COMPROBACIÓN

### ¿Qué hizo que el Nivel 3 produjera el mejor resultado?

**A)** Tenía más palabras y era más detallado

**B)** Incluía ejemplos concretos de cómo clasificar

**C)** Usaba un rol más específico que los anteriores

**D)** Estaba mejor formateado con secciones claras

> 🕐 30 segundos para pensar → levanten la mano

---

## 🎯 COMPROBACIÓN-RESPUESTA

**Respuesta correcta: B**

### Análisis:

- **A:** ❌ Más palabras sin dirección clara no mejoran el resultado
- **B:** ✅ Los ejemplos enseñan el CRITERIO — la IA VE cómo quieres que clasifique
- **C:** ❌ El rol ayuda, pero sin ejemplos el output sigue siendo inconsistente
- **D:** ❌ El formato ayuda a organizar, pero los ejemplos son los que calibran

> **Regla memorable:** Mostrar > Describir. Un ejemplo vale más que mil instrucciones.

---

## Concepto Clave: Framework RICE

| Letra | Pregunta | Tip |
|-------|----------|-----|
| **R** | ¿Quién debe ser la IA? | Específico > "experto" |
| **I** | ¿Qué debe hacer exactamente? | Verbo de acción |
| **C** | ¿Qué necesita saber? | Todo lo que evite que adivine |
| **E** | ¿Cómo debe verse el resultado? | **Mostrar > Describir** |

### Anti-patrón:
❌ "Sé breve pero detallado" — Instrucciones contradictorias

---

## Técnica Clave: Few-shot

### ¿Qué es?
Incluir 2-3 ejemplos de input → output para enseñar el patrón

### ¿Cuándo usar?
- Clasificación (como triage)
- Formato específico
- Criterio subjetivo que necesita calibrarse

### Ejemplo en acción:
```
Mensaje: "Producto llegó roto, es regalo de cumpleaños"
| 🔴 Alta | Envío | Reenvío express + cupón | 2h |

Mensaje: "¿Tienen descuento por volumen?"
| 🟢 Baja | Venta | Responder política | 24h |
```

---

## ⚠️ Las Limitaciones (Anti-Hype)

### 3 errores comunes que la IA comete en triage:

**1. Prioridad por lo que DICE vs lo que NECESITA**
> "No es urgente" pero tiene deadline real

**2. Categorías ambiguas**
> ¿Es consulta de venta o soporte de producto?

**3. Urgencia por tono vs urgencia real**
> Cliente enojado ≠ siempre mayor prioridad

### La lección:
La IA clasifica, pero TÚ validas. El juicio humano no es opcional.

---

## Lab Time

### Mi Sistema de Triage con IA

**Objetivo:** Construir un prompt de triage que evoluciona en 4 fases

**Tiempo:** 60 min

**Fases:**
1. El Caos (sin técnicas) — 10 min
2. +Rol — 15 min
3. +Formato — 15 min
4. +Few-shot — 15 min
5. Análisis crítico — 5 min

> 💡 Tip: Documenta cada versión para ver la evolución

---

## ✅ Checkpoint: Parte 1-2

### Verifica:
- [ ] Prompt básico ejecutado (caos documentado)
- [ ] Prompt con rol ejecutado
- [ ] Comparación anotada en Google Doc

**Pregunta:** ¿El rol mejoró el CRITERIO o el FORMATO?

---

## ✅ Checkpoint: Parte 3-4

### Verifica:
- [ ] Prompt con formato de tabla
- [ ] Prompt con ejemplos (few-shot)
- [ ] 5 mensajes clasificados en tabla final

**Pregunta:** ¿Los ejemplos calibraron mejor las prioridades?

---

## ✅ Checkpoint: Parte 5

### Verifica:
- [ ] Identificaste al menos 1 error de clasificación
- [ ] Anotaste por qué ocurrió
- [ ] Propusiste cómo corregirlo

**Pregunta para compartir:** ¿Qué error encontraste?

---

## 💡 Reflexión

### Hoy aprendiste:
- Framework RICE completo
- El poder de los ejemplos (Few-shot)
- Progresión iterativa: Rol → Formato → Ejemplos
- **Limitaciones reales de la IA**

### Pregunta para pensar:
¿Qué tareas de tu trabajo podrías convertir en sistemas de triage con IA?

---

## 📝 Entrega + Preview

### Tu entregable:
1. **Evolución del prompt** (4 versiones documentadas)
2. **Tabla de clasificación** (5 mensajes con tu prompt final)
3. **Reflexión crítica** (1 error encontrado + cómo corregirlo)

**Formato:** Google Doc con link público

### Próxima clase: Tu Copiloto de Contenido
De prompts individuales a flujos de trabajo completos → contenido profesional publicable
