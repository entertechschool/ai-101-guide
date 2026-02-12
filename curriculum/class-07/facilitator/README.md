# Guía del Facilitador - Clase 07: Mi Agente Real

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Transferencia**: Aplicar un patrón aprendido (agente PetShop) a un contexto nuevo (caso real del estudiante). Es la prueba de que el aprendizaje fue real.
- **Caso de uso real**: Proceso genuino del trabajo del estudiante, no un ejercicio ficticio. Debe involucrar clasificar, priorizar o decidir.
- **Iteración**: Ciclo de probar → encontrar errores → mejorar SystemPrompt → re-probar. El agente mejora con datos reales.
- **Clonación de escenario**: Duplicar un escenario en Make (Export/Import Blueprint) como base para construir uno nuevo.
- **Arquetipos**: Patrones comunes de triage por industria que sirven de punto de partida.

---

## Analogías Útiles

**PetShop = estacionamiento de autoescuela:**
PetShop fue el estacionamiento donde aprendiste a manejar sin riesgo. C07 es la primera vez en la calle real. Mismas habilidades, contexto diferente.

**Clonar escenario = tener rueditas que quitas pieza por pieza:**
No empiezas de cero — empiezas con algo que funciona y cambias una cosa a la vez.

**Tabla de arquetipos = menú en restaurante:**
Es más fácil elegir del menú que inventar un plato. Los arquetipos dan opciones concretas para quienes no identifican su caso.

---

## Contexto Pedagógico

### ¿Por qué transferencia?

C05-C06 demostraron que los estudiantes pueden **seguir instrucciones** para construir un agente. C07 demuestra que pueden **aplicar** lo aprendido a un contexto nuevo. Aquí es donde se valida el aprendizaje real.

### Riesgo principal

Estudiantes que no logran identificar su caso. La tabla de arquetipos es la solución — reduce la decisión de "inventa algo" a "elige uno y personaliza".

### Callbacks pedagógicos

| Clase | Técnica | Cómo se aplica en C07 |
|-------|---------|----------------------|
| C02 | RICE + Few-shot | Estructura del SystemPrompt para su caso |
| C03 | Socio pensante | Claude diseña el SystemPrompt con preguntas |
| C05 | Scaffolding Gemini | Gemini genera prompt para form v0 nuevo |
| C05-C06 | Arquitectura agente | Se clona y adapta, no se reconstruye |

---

## Preparación ANTES de Clase

### Crítico — Sin esto la clase no funciona

1. **Tu propio agente para caso DIFERENTE** (no PetShop)
   - Probado end-to-end: form → webhook → clasificación → email → Sheets
   - Será tu demo en vivo. Debe funcionar sin fallas
   - Prepara 3 mensajes de prueba para la demo

2. **6 arquetipos verificados** que funcionen con Grok Free
   - SystemPrompts de backup por arquetipo (por si alguien necesita ayuda)
   - Verifica que cada uno produce output en formato correcto

3. **Escenario de backup** para estudiantes atascados
   - Un escenario simple pre-clonado con categorías genéricas
   - Listo para compartir vía Blueprint export

4. **Tabla de arquetipos** lista para compartir (digital o impresa)

5. **Escenario pre-clonado** para quienes perdieron su C06
   - Blueprint del agente PetShop completo para import rápido

---

## Momentos Clave de la Clase

### Pregunta Detonadora (~5 min)

**Respuesta correcta: B** — Definir categorías y reglas de MI caso antes de tocar Make

**Script post-votación:**
```
"Si copias PetShop tal cual, tienes un agente que clasifica
mensajes de una tienda de mascotas. Inútil para tu trabajo.
PRIMERO defines TU caso — categorías, reglas, acciones.
DESPUÉS adaptas la arquitectura. El orden importa."
```

---

### Demo: Tu Agente Propio (~10 min)

Muestra tu agente (caso diferente a PetShop):

1. Explica brevemente: "Mi caso es [X]. Mis categorías son [A, B, C]."
2. Envía un mensaje desde tu formulario
3. Muestra en Make History cómo clasifica
4. Muestra el email con la categoría correcta
5. Muestra el registro en Sheets

**Script clave:**
```
"Mismo patrón que PetShop. Caso diferente.
No seguí ningún tutorial nuevo para esto.
Apliqué lo que ya sabía. Eso es transferencia."
```

---

### Momento WOW: Primer mensaje real clasificado

Cuando el estudiante envía SU primer mensaje real desde SU formulario y ve la clasificación correcta en SU caso — ese es el WOW moment más potente del módulo. Es más impactante que C05 porque es **su caso real**, no PetShop.

```
"Miren su Sheets. Ese registro es de SU proceso.
SU agente clasificó SU mensaje. Eso no lo hizo un tutorial."
```

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No sé qué caso elegir" | No identifica patrón en su trabajo | Tabla de arquetipos + "¿Qué haces 5+ veces/semana que involucra decidir?" |
| "Mi caso no encaja en triage" | Piensa muy literalmente | "¿Clasificas, priorizas o decides algo? Eso es triage" |
| "Copié pero no funciona" | Filters aún dicen URGENTE/CONSULTA/VENTA | Cambiar a nuevas categorías — case-sensitive |
| "SystemPrompt no clasifica bien" | Reglas vagas o ambiguas | "¿Tiene 3 categorías explícitas con reglas diferenciadas?" |
| "No tengo 5 mensajes reales" | No preparó antes de clase | "Inventa 5 basados en experiencia. En la tarea, usa reales" |
| "Router toma ruta equivocada" | Case sensitivity en Filters | Filter debe matchear EXACTO el output del SystemPrompt |
| "Es igual que C06" | Ve la arquitectura, no el contenido | "La arquitectura sí. La TRANSFERENCIA es el aprendizaje" |
| "Perdí mi escenario C06" | Problema técnico | Compartir escenario pre-clonado de backup |

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~5 | PD votada | Discusión caso vs tutorial completada |
| ~15 | Demo completada | Preguntas sobre el caso del facilitador |
| ~35 | Caso diseñado | "¿Quién tiene 3 categorías con reglas?" |
| ~50 | Escenario clonado | "¿Quién duplicó su escenario en Make?" |
| ~65 | Form v0 creado | "¿Quién tiene form nuevo deployado?" |
| ~90 | Make adaptado | "¿Quién tiene todos los módulos actualizados?" |
| ~110 | Form conectado | "¿Quién envía desde su form al webhook?" |
| ~130 | 5 mensajes probados | "¿Quién tiene resultados en Sheets?" |
| ~140 | Mejora documentada | "¿Quién encontró y corrigió al menos 1 error?" |

---

## Sección Anti-Hype

**Script para el momento de pruebas:**
```
"Tu agente va a tener las mismas fallas que PetShop.
Nuevo caso, mismos tipos de errores.
Pero ahora sabes CÓMO arreglarlos.
Esa es la diferencia entre seguir un tutorial y saber CONSTRUIR."
```

**Mensaje clave:**
Un agente imperfecto para tu caso real vale más que un agente perfecto de tutorial.

---

## Tips de Facilitación

### Si el grupo avanza rápido:
- Agregar 4ta categoría o lógica condicional más compleja
- Probar con mensajes ambiguos que estresen al agente
- Que ayuden a compañeros que están atascados

### Si alguien está intimidado:
- Emparejar con alguien que va bien
- Empezar del arquetipo más cercano, no inventar desde cero
- "Vuelve a la tabla. Elige uno. Personalizamos después."

### Si alguien no identifica su caso:
- "¿Recibes emails que clasificas? ¿Mensajes que priorizas? ¿Solicitudes que filtras?"
- Si realmente no tiene caso: que use un arquetipo de la tabla como si fuera su caso
- La habilidad de transferencia se practica igual

### Manejo de tiempo:
- Parte 1 (diseñar) es donde más se atoran. Si a los 25 min no tienen caso, intervén.
- Parte 2 (construir) fluye si el caso está definido.
- Parte 3 (probar) siempre se queda corta — priorizar al menos 3 mensajes.

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

```
"Próxima clase presentan ESTE agente en vivo.
No slides. No documento. Tu agente funcionando.
5 minutos. Alguien del público envía un mensaje.
El agente debe funcionar."
```

**Tarea para la próxima clase:**
1. Pulir el agente — que los 5 mensajes clasifiquen correctamente
2. Preparar 5 mensajes de prueba listos para que el público los envíe
3. Ensayar presentación de 5 min: Problema → Agente → Demo → Aprendizaje
4. Tener cuenta de LinkedIn abierta
