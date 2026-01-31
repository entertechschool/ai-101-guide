# Lab 03: Mi Sistema Clarificador de Ideas

Construirás un Claude Project que funciona como tu "socio pensante" — un sistema que te hace preguntas para extraer y estructurar tu conocimiento. Al terminar, tendrás un framework documentado que captura algo que sabías pero nunca habías formalizado.

> ⏱️ **Tiempo total:** 70 minutos

### 🎯 Objetivo

Crear un Claude Project con instrucciones de clarificador de ideas, y usarlo para extraer UN framework o proceso de tu propia expertise.

---

## El Cambio de Paradigma

| Clases 01-02 | Clase 03 |
|--------------|----------|
| Tú escribes prompt → IA responde | IA pregunta → Tú respondes |
| Output = contenido genérico de IA | Output = TU conocimiento estructurado |
| Prompt único | Sistema reusable (Project) |

---

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Claude abierto | Cuenta activa con acceso a Projects |
| Perplexity abierto | Para mini-research |
| Conocimiento identificado | Algo que sabes y quieres documentar |
| Google Doc | Para capturar tu framework final |

**Nota:** Claude Projects está disponible en todas las cuentas (gratuitas y Pro).

---

## Parte 1: Identifica Tu Conocimiento Oculto (10 min)

Antes de configurar el sistema, necesitas elegir QUÉ vas a clarificar.

### 1.1 Ejemplos de conocimiento clarificable

| Tipo | Ejemplo | Output esperado |
|------|---------|-----------------|
| **Proceso de evaluación** | "Cómo evalúo si un candidato es bueno" | Guía de entrevista con 5-7 criterios |
| **Criterios de decisión** | "Cómo priorizo qué proyectos hacer" | Matriz de priorización |
| **Proceso operativo** | "Cómo hago onboarding de clientes" | Checklist de 10-15 pasos |
| **Evaluación de riesgo** | "Cómo detecto si un proveedor va a fallar" | Lista de red flags y green flags |
| **Metodología propia** | "Cómo escribo propuestas que ganan" | Template con secciones clave |

### 1.2 Elige TU tema

Escribe en tu Google Doc:

```
CONOCIMIENTO A CLARIFICAR:
_________________________________

¿Por qué lo elegí?
- Lo hago bien: ___
- Me lo preguntan frecuentemente: ___
- Nunca lo he documentado formalmente: ___
```

### 1.3 Verifica que es clarificable

Tu tema debe cumplir:
- [ ] Es algo que TÚ sabes (no que quieres aprender)
- [ ] Tiene pasos o criterios (aunque no los tengas escritos)
- [ ] Alguien más podría beneficiarse de saberlo

✅ **Checkpoint:** Tienes UN tema específico para clarificar.

---

## Parte 1.5: Mini-Research con Perplexity (10 min)

Antes de configurar tu clarificador, investiga contexto sobre tu tema.

### 1.5.1 Abre Perplexity

1. Ve a [perplexity.ai](https://perplexity.ai)
2. Inicia sesión con tu cuenta

### 1.5.2 Investiga mejores prácticas

Busca: "mejores prácticas [TU TEMA] [TU INDUSTRIA]"

**Ejemplo:** "mejores prácticas evaluación de proveedores software"

### 1.5.3 Guarda 2-3 insights

En tu Google Doc, anota:

```
MINI-RESEARCH:
- Insight 1: ___
- Insight 2: ___
- Fuente: [URL]
```

> 💡 Este mini-research te dará contexto para responder mejor
> las preguntas del clarificador.

✅ **Checkpoint:** Tienes 2-3 insights documentados.

---

## Parte 2: Configura Tu Claude Project (15 min)

Ahora crearás el sistema clarificador como un Claude Project.

### 2.1 Crear el Project

1. Ve a [claude.ai](https://claude.ai)
2. En el sidebar izquierdo, haz clic en **"Projects"**
3. Clic en **"+ Create Project"**
4. Nombre: `Mi Clarificador de Ideas`
5. Descripción: `Sistema para extraer y estructurar mi conocimiento`

### 2.2 Configurar las instrucciones del Project

En la sección **"Custom Instructions"** del Project, pega esto:

```
Eres mi socio pensante — un experto en extraer y estructurar conocimiento tácito.

TU OBJETIVO:
Ayudarme a documentar algo que sé hacer pero nunca he formalizado.
El output final será MÍO — mi expertise estructurada, no contenido genérico.

CÓMO DEBES TRABAJAR:

1. FASE DE EXPLORACIÓN (primeras 5-8 preguntas)
- Haz UNA pregunta a la vez
- Espera mi respuesta antes de continuar
- Busca los patrones detrás de mis respuestas
- Pregunta "¿por qué?" cuando detectes decisiones implícitas

2. FASE DE ESTRUCTURACIÓN (cuando tengas suficiente info)
- Propón una estructura (lista, matriz, checklist, framework)
- Muéstrame el borrador y pregunta qué falta
- Itera basándote en mis correcciones

3. FASE DE VALIDACIÓN (al final)
- Presenta el framework completo
- Pregunta: "¿Esto captura lo que realmente haces?"
- Ajusta según mi feedback

REGLAS IMPORTANTES:
- Nunca asumas que sabes las respuestas — PREGUNTA
- Si digo "depende", pregunta: "¿De qué depende específicamente?"
- Busca los criterios ocultos detrás de mis "intuiciones"
- El resultado debe ser algo que yo pueda usar y compartir

FORMATO DE OUTPUT FINAL:
Al terminar, entrega un documento estructurado con:
- Título descriptivo
- Contexto/cuándo usar esto
- Pasos, criterios o framework principal
- Notas o excepciones importantes
```

### 2.3 Guardar el Project

Haz clic en **"Save"** o **"Create Project"**.

✅ **Checkpoint:** Tienes un Claude Project configurado con instrucciones de clarificador.

---

## Parte 3: Extrae Tu Framework (25 min)

Ahora viene la magia. Vas a conversar con tu socio pensante.

### 3.1 Inicia la conversación

Abre una nueva conversación dentro de tu Project y escribe:

```
Quiero documentar mi proceso de [TU TEMA].

Es algo que hago bien pero nunca he formalizado.
Ayúdame a extraer los pasos/criterios que realmente uso.
```

### 3.2 Responde las preguntas con honestidad

La IA te hará preguntas como:
- "¿Cuál es el primer paso que haces cuando...?"
- "¿Qué señales buscas para saber si...?"
- "¿Cuándo decides que algo es suficiente vs insuficiente?"
- "¿Qué errores has visto que otros cometen?"

**Tips para responder:**
- Sé específico, no genérico
- Si dices "depende", explica de qué
- Menciona ejemplos reales (anonimizados si es necesario)
- Si algo "lo sientes", intenta describir qué observas

### 3.3 Guía la estructuración

Cuando la IA proponga una estructura, evalúa:
- ¿Captura lo que realmente hago?
- ¿Falta algo importante?
- ¿Hay algo que sobra o confunde?

Dile directamente:
- "Falta el paso de..."
- "Esto no lo hago así, más bien..."
- "Agregaría una excepción para cuando..."

### 3.4 Valida el framework final

Cuando tengas el borrador completo, pregúntate:
- ¿Podría alguien más seguir esto y obtener resultados similares?
- ¿Me sentiría cómodo compartiendo esto con mi equipo?
- ¿Captura mi forma real de trabajar, no una versión idealizada?

✅ **Checkpoint:** Tienes un framework documentado basado en TU expertise.

---

## Parte 4: Reflexión y Documentación (10 min)

### 4.1 Copia tu framework al Google Doc

Toma el output final de Claude y pégalo en tu Google Doc.

### 4.2 Agrega reflexión personal

Debajo del framework, escribe:

```
REFLEXIÓN:

1. ¿Qué descubrí que no sabía que sabía?
___

2. ¿Qué paso o criterio me sorprendió al verbalizarlo?
___

3. ¿Cómo podría usar este framework en mi trabajo?
___

4. ¿A quién podría compartirle esto?
___
```

### 4.3 Compara con el patrón anterior

Piensa en la diferencia:
- Clase 02: Tú le dijiste a la IA qué hacer → Output de la IA
- Clase 03: La IA te preguntó → Output TUYO estructurado

¿Cuál se siente más valioso? ¿Por qué?

✅ **Checkpoint:** Tienes reflexión documentada.

---

## 📝 Entregable

**Google Doc con 3 secciones:**

### 1. Claude Project configurado
- Screenshot del Project con las instrucciones visibles
- O el texto de las instrucciones si usaste prompt largo

### 2. Framework extraído
- Tu conocimiento documentado
- Debe tener estructura clara (pasos, criterios, checklist, etc.)
- Debe ser algo que puedas compartir y usar

### 3. Reflexión
- ¿Qué descubriste que no sabías que sabías?
- ¿Cómo cambia tu visión de usar IA?

**Entrega:** Link público del Google Doc.

> 📌 **Importante:** Guarda bien este framework — lo usarás como base para tu Proyecto Integrador en la próxima clase.

---

## Checklist Final

- [ ] ¿Configuré el Claude Project (o prompt de sistema)?
- [ ] ¿Tuve una conversación de exploración real con la IA?
- [ ] ¿Mi framework captura conocimiento MÍO, no genérico?
- [ ] ¿Podría alguien más usar este framework?
- [ ] ¿Documenté mi reflexión sobre el proceso?

---

## 🚀 Bonus: Segundo Framework (Opcional)

Si terminaste antes, intenta clarificar un segundo tema:

1. Elige algo diferente de tu primer framework
2. Usa el mismo Project (el sistema ya está configurado)
3. Compara: ¿Fue más fácil la segunda vez?

**Ideas para segundo framework:**
- Si el primero fue "cómo evaluar", prueba "cómo decidir"
- Si el primero fue operativo, prueba algo estratégico
- Si el primero fue individual, prueba algo de equipo
