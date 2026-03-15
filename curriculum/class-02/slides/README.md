<!-- .slide: data-background="#0A192F" -->

# Clase 02: Diseño de instrucciones efectivas
## De resultados mediocres a extraordinarios

*AI 101 — EnterTech School*

---

## 🔗 TRANSICIÓN: Clase 01 → Clase 02

### Clase anterior:
- Construiste tu primer SISTEMA con Claude
- Fórmula: `ROL + CONTEXTO + INSTRUCCIÓN`

### Hoy:
- Evolucionamos a **RICE** (+ Ejemplo)
- El Ejemplo es el upgrade que transforma resultados

> "La IA no me da buenos resultados" — ¿Seguro que el problema es la IA?

---

## 🧠 QUIZ PRE-LAB

### ¿Cuál elemento de un prompt hace MÁS diferencia en la calidad del resultado?

**A)** El rol que le asignas a la IA

**B)** La longitud y detalle del prompt

**C)** Los ejemplos de output deseado

**D)** Las palabras que usas al inicio

*Toma 2-3 respuestas antes de continuar*

---

## 🎬 Demo: Triage de Mensajes — 3 Niveles

### El Caso: PetShop Express — 5 mensajes, ¿cuál atender primero?

**Nivel 1 — Casual:**
> "Clasifica estos mensajes de clientes."

**Nivel 2 — Con Rol:**
> "Eres agente de soporte senior... Clasifica."

**Nivel 3 — RICE Completo:**
> Rol + Formato tabla + **Ejemplos de clasificación**

---

## 🎯 COMPROBACIÓN

### ¿Qué hizo que el Nivel 3 produjera el mejor resultado?

**A)** Tenía más palabras y era más detallado

**B)** Incluía ejemplos concretos de cómo clasificar

**C)** Usaba un rol más específico que los anteriores

**D)** Estaba mejor formateado con secciones claras

> 🕐 30 segundos para pensar → levanten la mano

---

## 🎯 COMPROBACIÓN — Respuesta

**Respuesta correcta: B**

- **A:** ❌ Más palabras sin dirección no mejoran el resultado
- **B:** ✅ Los ejemplos enseñan el CRITERIO — la IA VE cómo clasificar
- **C:** ❌ El rol ayuda, pero sin ejemplos el output es inconsistente
- **D:** ❌ El formato organiza, pero los ejemplos calibran

> **Regla memorable:** Mostrar > Describir. Un ejemplo vale más que mil instrucciones.

---

## 📐 Concepto Clave: Framework RICE

| Letra | Pregunta | Tip |
|-------|----------|-----|
| **R** | ¿Quién debe ser la IA? | Específico > "experto" |
| **I** | ¿Qué debe hacer exactamente? | Verbo de acción |
| **C** | ¿Qué necesita saber? | Todo lo que evite que adivine |
| **E** | ¿Cómo debe verse el resultado? | **Mostrar > Describir** |

> Evolución: `SISTEMA` (Clase 01) → `RICE` (Clase 02) — se agrega el Ejemplo.

---

## 🔑 Few-shot + ⚠️ Limitaciones

### Few-shot: incluir 2-3 ejemplos input → output

Usar cuando: clasificación, formato específico, criterio subjetivo <!-- .element: class="fragment" -->

### 3 errores comunes de la IA en triage:

1. **Prioriza por TONO, no por necesidad real** <!-- .element: class="fragment" -->
2. **Categorías ambiguas** (¿venta o soporte?) <!-- .element: class="fragment" -->
3. **Se cree lo que dice el cliente** ("no es urgente" pero tiene deadline) <!-- .element: class="fragment" -->

> La IA clasifica, TÚ validas. El juicio humano no es opcional.

---

## 🔬 Lab Time: Mi Sistema de Triage

**Objetivo:** Prompt de triage que evoluciona en 5 partes

**Tiempo:** 70 min

| Parte | Técnica | Tiempo |
|-------|---------|--------|
| 1 | El Caos (sin técnicas) | 10 min |
| 2 | +Rol | 15 min |
| 3 | +Formato | 15 min |
| 4 | +Few-shot | 15 min |
| 5 | Análisis Crítico | 10 min |

---

## ✅ CHECKPOINT: Parte 1-2

### Debes ver en pantalla:
- [ ] Clasificación caótica (Parte 1) documentada
- [ ] Clasificación con rol (Parte 2) documentada
- [ ] Comparación anotada en Google Doc

**¿El rol mejoró el CRITERIO o el FORMATO?**

**Problemas comunes:**
- Resultado casi igual → Verificar que el rol sea específico, no genérico

---

## ✅ CHECKPOINT: Parte 3-5

### Debes ver en pantalla:
- [ ] Tabla con 5 mensajes clasificados (Parte 3-4)
- [ ] Prompt con ejemplos few-shot ejecutado
- [ ] 1 error de la IA identificado y documentado (Parte 5)

**¿Los ejemplos calibraron mejor las prioridades?**

**Problemas comunes:**
- IA no mantiene formato → Revisar que los ejemplos usen exactamente la tabla

---

## 💡 REFLEXIÓN

### Hoy aprendiste:

- RICE = ROL + INSTRUCCIÓN + CONTEXTO + **EJEMPLO**
- Few-shot: mostrar ejemplos > describir reglas
- Progresión iterativa: Caos → Rol → Formato → Ejemplos
- La IA clasifica, pero TÚ validas

### Preguntas de cierre:

1. ¿Por qué "mostrar" es más poderoso que "describir"?
2. ¿Qué tarea de tu trabajo convertirías en sistema de triage?
3. ¿Qué limitación de la IA te sorprendió más?

---

## 📝 Entrega

### Biblioteca personal: mínimo 3 prompts

1. **Prompt de triage** — RICE + Few-shot + tabla clasificada
2. **Prompt para TU trabajo** — RICE aplicado a tarea real
3. **Reflexión crítica** — 1 error encontrado + corrección propuesta

**Formato:** Google Doc con link público

### Próxima clase: Producción de contenido profesional con IA
De prompts individuales a **Claude Projects** + frameworks personales
