# Lab 08: Mi Demo Day

## Objetivo

Presentar tu agente en vivo, publicar tu caso en LinkedIn y crear un plan de desarrollo para los próximos 30 días.

> ⏱️ **Tiempo estimado:** 60 minutos (sin contar test previo)

---

## Antes de empezar

| ✅ | Requisito |
|----|-----------|
| | Agente C07 funcionando (5+ módulos, probado) |
| | 5 mensajes de prueba listos para el público |
| | LinkedIn abierta |
| | Google Doc C05-C07 actualizado |

### Test Diagnóstico M2 (15 min, pre-lab)

- 8 preguntas de opción múltiple
- No afecta calificación — **"es un espejo, no un examen"**
- El facilitador comparte el link (Google Forms)
- Individual, sin consultar materiales

> ✅ **Checkpoint:** Test completado

---

## Parte 1: Pulir + Peer Review (10 min)

### 1.1 Últimos ajustes al agente (5 min)

- Envía 2 mensajes más desde tu formulario
- Verifica en Google Sheets que clasifique correctamente
- Si algo falla, corrige el SystemPrompt o los Filters

### 1.2 Peer review (5 min)

1. Intercambia la URL de tu formulario con un compañero
2. Tu compañero envía 1 mensaje a TU agente
3. ¿Clasificó correctamente? Feedback en 1 oración

> ✅ **Checkpoint:** Agente probado por un par

---

## Parte 2: Presentaciones (50-60 min)

### Formato: 5 min por persona — DEMO EN VIVO

No slides. No documento. Tu agente funcionando.

#### Estructura de la presentación:

**1. Mi problema (30 seg)**
> "En mi trabajo, [X] me costaba [Y tiempo/esfuerzo]"

**2. Mi agente (2 min)**
- Mostrar Make brevemente (no explicar cada módulo)
- Explicar tus 3 categorías + reglas principales
- Mencionar qué adaptaste de PetShop

**3. Demo en vivo (1.5 min)**
- **ALGUIEN DEL PÚBLICO** envía un mensaje desde tu formulario
- Mostrar en Make History cómo clasifica en tiempo real
- Mostrar el email que llega con la categoría correcta
- Mostrar el registro en Google Sheets

**4. Lo que aprendí (1 min)**
- 1 error que encontraste + cómo lo corregiste
- 1 limitación honesta de tu agente

#### Feedback de pares (1-2 min post-presentación)

Después de cada presentación, el grupo da feedback:
- **1 fortaleza:** "Me convenció cuando..."
- **1 sugerencia:** "Sería más fuerte si..."

#### Criterios de evaluación

| Criterio | Pregunta |
|----------|----------|
| Problema claro | ¿Se entiende qué resuelve el agente? |
| Agente funciona | ¿Clasificó correctamente en vivo? |
| Categorías reales | ¿Reflejan un caso genuino de trabajo? |
| Aprendizaje honesto | ¿Documentó errores y limitaciones? |

> 💡 **Grupos grandes (10+):** Reducir a 3 min por persona o hacer rondas paralelas.

> ⚠️ **Si tu demo falla en vivo:** Abre Make History y muestra un run exitoso anterior (máx 30 seg extra). Lo importante es demostrar que el agente funciona, no que la demo en vivo sea perfecta.

> ✅ **Checkpoint:** Presentación completada + feedback recibido

---

## Parte 3: LinkedIn + Roadmap (15 min)

### 3.1 Escribir/finalizar LinkedIn post (7 min)

Template para tu post:

```
[HOOK: 1 línea que capture atención]

[QUÉ CONSTRUÍ: 2-3 líneas describiendo tu agente]

[RESULTADO: 1-2 líneas con métrica real]

[TAKEAWAY: 1 línea de aprendizaje]
```

**Ejemplo realista:**

```
Automaticé la clasificación de leads que me tomaba 2 horas diarias.

Construí un agente IA que recibe solicitudes, las clasifica
en CALIENTE/TIBIO/FRÍO y me notifica por email con la prioridad.

Resultado: 45 mensajes clasificados automáticamente esta semana.
Precisión del 80% en el primer intento.

Lo más importante: el agente no reemplaza mi criterio.
Me ahorra el trabajo repetitivo para enfocarme en las decisiones
que realmente importan.
```

### 3.2 Publicar juntos (3 min)

El facilitador cuenta:

> **"3... 2... 1... PUBLICAR!"**

Todos publican al mismo tiempo. Screenshot del post publicado.

### 3.3 Roadmap 30 días con Claude (5 min)

Abre Claude y usa este prompt:

```
Construí un agente de triage que clasifica [tipo de mensajes]
en [categorías] usando Make + OpenRouter + Gmail + Google Sheets.

Ayúdame a crear un plan de 30 días:
- Semana 1: Mejorar precisión del agente actual
- Semana 2: Expandir a más categorías o casos edge
- Semana 3: Aplicar el patrón a otro proceso de mi trabajo
- Semana 4: Medir impacto real y documentar resultados

Dame 3 quick-wins que pueda hacer ESTA SEMANA.
```

> ✅ **Checkpoint:** LinkedIn publicado + plan de 30 días creado

---

## Entregable final

1. **Presentación completada** — Verificación del facilitador (no necesitas entregar slides)
2. **LinkedIn post publicado** — Screenshot + link al post
3. **Plan 30 días** — Con 3 quick-wins concretos para esta semana

**Formato:** Agregar al Google Doc de C05-C07 como sección final "C08: Demo Day"
