# Lab 04: Mi Proyecto Integrador M1

Este es el proyecto de cierre del Módulo 1. Integrarás todo lo aprendido — sistema (Clase 01), prompting (Clase 02), clarificación (Clase 03), más research — para resolver un problema real de tu trabajo. El resultado es calificable y será parte de tu portfolio.

> ⏱️ **Tiempo total:** 90 minutos

### 🎯 Objetivo

Crear un proyecto completo que resuelve un problema real usando múltiples habilidades de IA, documentado con antes/después medible.

---

## Lo que Integrarás

| De Clase | Habilidad | Cómo la usarás |
|----------|-----------|----------------|
| 01 | Sistemas reusables | Tu solución será un sistema, no un prompt único |
| 02 | RICE + Few-shot | Aplicarás estructura y ejemplos en tu prompt |
| 03 | Clarificación + Perplexity | Estructurarás tu enfoque + research con fuentes |
| **Nuevo** | Deep Research | Investigación profunda con Gemini |
| **Nuevo** | Gems | Crearás un asistente especializado |

---

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Problema real identificado | Algo de tu trabajo que quieres mejorar |
| Claude abierto | Para sistema/prompts |
| Gemini abierto | Para Deep Research + Gem |
| Perplexity abierto | Para research con fuentes |
| Google Doc nuevo | Para documentar el proyecto |

---

## Parte 1: Define Tu Problema (10 min)

### 1.1 Elige un problema real

Tu problema debe cumplir:
- [ ] Es algo de TU trabajo (no hipotético)
- [ ] Te consume tiempo o genera fricción
- [ ] Tiene solución (no solo es una queja)
- [ ] Puedes medir mejora (antes/después)

**Ejemplos que funcionan:**

| Problema | Por qué funciona |
|----------|------------------|
| "Respondo las mismas preguntas de clientes 5x por semana" | Medible, repetitivo, solucionable |
| "Mis propuestas no tienen estructura consistente" | Afecta resultados, sistematizable |
| "No tengo criterios claros para priorizar proyectos" | Impacta decisiones, clarificable |
| "Los reportes semanales me toman 3 horas" | Tiempo medible, automatizable |

### 1.2 Documenta el "antes"

En tu Google Doc, escribe:

```
## Mi Proyecto Integrador M1

### 1. El Problema
**Descripción:** [Qué problema resuelves]

**Impacto actual (el "antes"):**
- Tiempo que consume: ___
- Frecuencia: ___
- Fricción que genera: ___
- Consecuencias de no resolverlo: ___

**Meta (el "después"):**
- ¿Cómo se vería resuelto?
- ¿Qué métrica mejoraría?
```

✅ **Checkpoint:** Tienes problema definido con "antes" documentado.

---

## Parte 2: Research con Fuentes (15 min)

Ahora investigas contexto externo que enriquezca tu solución.

### 2.1 Elige tu herramienta de research

| Herramienta | Cuándo usarla |
|-------------|---------------|
| **Perplexity** (ya conoces de Clase 03) | Preguntas específicas, necesitas fuentes rápidas |
| **Gemini Deep Research** | Investigación profunda, múltiples ángulos |

### 2.2 Conduce el research

**En Perplexity:**
1. Ve a [perplexity.ai](https://perplexity.ai)
2. Haz 2-3 búsquedas relacionadas con tu problema
3. Guarda las fuentes relevantes

**En Gemini (Deep Research):**
1. Ve a [gemini.google.com](https://gemini.google.com)
2. Activa "Deep Research" si está disponible
3. Pide investigación sobre tu tema

**Preguntas de research sugeridas:**
- "Mejores prácticas para [tu problema] en [tu industria]"
- "Cómo empresas resuelven [tu problema]"
- "Frameworks para [tu área de problema]"

### 2.3 Documenta hallazgos

En tu Google Doc, agrega:

```
### 2. Research

**Fuentes consultadas:**
1. [Título] - [URL] - Hallazgo clave
2. [Título] - [URL] - Hallazgo clave
3. [Título] - [URL] - Hallazgo clave

**Insights relevantes:**
- Insight 1: ___
- Insight 2: ___
- Insight 3: ___

**Cómo aplica a mi problema:**
___
```

✅ **Checkpoint:** Tienes research con al menos 3 fuentes citadas.

---

## Parte 3: Clarifica Tu Enfoque (15 min)

Usas técnicas de Clase 03 para estructurar tu solución.

### 3.1 Abre tu Claude Project clarificador

(El que configuraste en Clase 03, o crea uno nuevo)

### 3.2 Clarifica tu enfoque

Inicia conversación:

```
Quiero resolver [TU PROBLEMA].

Ya investigué y encontré que [RESUMEN DE RESEARCH].

Ayúdame a estructurar MI enfoque para resolverlo.
¿Qué preguntas me harías para entender cómo debería abordarlo?
```

### 3.3 Responde las preguntas

La IA te preguntará cosas como:
- "¿Qué has intentado antes?"
- "¿Cuál es el obstáculo principal?"
- "¿Qué recursos tienes disponibles?"
- "¿Cómo sabrías que funcionó?"

### 3.4 Documenta el enfoque

En tu Google Doc:

```
### 3. Mi Enfoque

**Estructura de la solución:**
- Paso 1: ___
- Paso 2: ___
- Paso 3: ___

**Criterios de éxito:**
- ___
- ___

**Lo que aprendí al clarificar:**
___
```

✅ **Checkpoint:** Tienes enfoque estructurado documentado.

---

## Parte 4: Crea Tu Sistema (30 min)

Ahora construyes la solución reusable.

### 4.1 Decide qué tipo de sistema crear

| Tipo | Cuándo elegirlo |
|------|-----------------|
| **Prompt maestro (Claude)** | Tarea repetitiva que resuelves con instrucciones |
| **Claude Project** | Necesitas contexto persistente y archivos |
| **Gem de Gemini** | Quieres asistente especializado en Google |

### 4.2 Crea tu Gem de Gemini

Todos deben crear un Gem como parte del proyecto:

1. Ve a [gemini.google.com](https://gemini.google.com)
2. En el menú lateral, busca **"Gems"** o **"Gem manager"**
3. Clic en **"New Gem"** o **"Create"**
4. Configura:
   - **Nombre:** [Relacionado con tu problema]
   - **Instrucciones:** Tu system prompt especializado

**Template para instrucciones del Gem:**

```
Eres mi asistente especializado en [TU ÁREA].

Mi contexto:
- Rol: [tu rol]
- Industria: [tu industria]
- Objetivo: [qué necesitas lograr]

Tu trabajo:
[Describe qué debe hacer el Gem cuando le hables]

Formato de respuestas:
[Cómo debe estructurar sus outputs]

Restricciones:
[Qué NO debe hacer o asumir]
```

### 4.3 Crea tu prompt/sistema adicional

Además del Gem, crea al menos UN sistema en Claude:
- Un prompt maestro con RICE + Few-shot
- O un Claude Project con instrucciones

### 4.4 Prueba tu sistema

1. Usa tu Gem con un caso real
2. Usa tu prompt/Project con un caso real
3. Evalúa: ¿Produce el resultado esperado?

### 4.5 Documenta el sistema

En tu Google Doc:

```
### 4. Mi Sistema/Solución

**Gem de Gemini:**
- Nombre: ___
- Instrucciones: [copia las instrucciones]
- Screenshot del Gem funcionando

**Sistema adicional (Claude):**
- Tipo: [Prompt / Project]
- Contenido: [copia el prompt o instrucciones]
- Screenshot funcionando

**Prueba con caso real:**
- Input de prueba: ___
- Output obtenido: ___
- ¿Funciona? [Sí/No/Parcialmente]
- Ajustes necesarios: ___
```

✅ **Checkpoint:** Tienes Gem + sistema adicional documentados.

---

## Parte 5: Documenta el "Después" (10 min)

### 5.1 Mide la mejora

Compara con tu "antes":

| Métrica | Antes | Después | Mejora |
|---------|-------|---------|--------|
| Tiempo | ___ | ___ | ___% |
| Esfuerzo | ___ | ___ | ___% |
| Calidad | ___ | ___ | ___% |

### 5.2 Reflexiona sobre el proceso

En tu Google Doc:

```
### 5. Resultados y Reflexión

**Antes vs Después:**
[Tabla de métricas]

**¿Qué funcionó bien?**
___

**¿Qué ajustaría?**
___

**¿Cómo usaré esto en el futuro?**
___

**Lo más valioso que aprendí:**
___
```

### 5.3 Revisa completitud

Verifica que tu documento tiene:
- [ ] Problema definido con "antes"
- [ ] Research con fuentes citadas
- [ ] Enfoque estructurado
- [ ] Gem de Gemini configurado
- [ ] Sistema adicional (Claude)
- [ ] Prueba con caso real
- [ ] "Después" con métricas
- [ ] Reflexión

✅ **Checkpoint:** Proyecto completo documentado.

---

## 📝 Entregable

**Google Doc completo con 5 secciones:**

### 1. El Problema
- Descripción clara
- Impacto actual (el "antes")
- Meta esperada

### 2. Research
- 3+ fuentes citadas con URLs
- Insights relevantes
- Cómo aplica a tu problema

### 3. Mi Enfoque
- Estructura de la solución
- Criterios de éxito

### 4. Mi Sistema/Solución
- **Gem de Gemini** (screenshot + instrucciones)
- **Sistema Claude** (prompt o Project)
- Prueba con caso real

### 5. Resultados y Reflexión
- Antes vs después (métricas)
- Reflexión sobre el proceso

**Entrega:** Link público del Google Doc.

---

## Criterios de Evaluación

| Criterio | Peso | Qué se evalúa |
|----------|------|---------------|
| **Problema real** | 20% | ¿Es genuino y tiene impacto medible? |
| **Research** | 20% | ¿Hay fuentes verificables y relevantes? |
| **Clarificación** | 20% | ¿El enfoque está bien estructurado? |
| **Sistema** | 25% | ¿El Gem y sistema funcionan? ¿Son reusables? |
| **Documentación** | 15% | ¿Está completo con antes/después? |

---

## Checklist Final

- [ ] ¿Mi problema es real y tiene impacto medible?
- [ ] ¿Tengo al menos 3 fuentes de research citadas?
- [ ] ¿Mi enfoque está estructurado con pasos claros?
- [ ] ¿Configuré un Gem de Gemini funcional?
- [ ] ¿Tengo un sistema adicional en Claude?
- [ ] ¿Probé ambos con un caso real?
- [ ] ¿Documenté antes/después con métricas?
- [ ] ¿Escribí reflexión sobre el proceso?

---

## 🚀 Bonus: Presentación (5 min)

Si el tiempo lo permite, prepara un pitch de 2 minutos:

1. **El problema** (20 seg): "Yo tenía [problema] que me costaba [impacto]"
2. **La solución** (40 seg): "Creé [sistema] que [qué hace]"
3. **El resultado** (30 seg): "Ahora [métrica mejoró] de [antes] a [después]"
4. **Demo rápida** (30 seg): Muestra tu Gem o sistema en acción
