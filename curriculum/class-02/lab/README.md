# Lab 02: Mis Prompts Maestros

En este lab transformarás prompts básicos en prompts profesionales usando el framework RICE. Competirás con tus compañeros en un Prompt Battle y crearás 3 prompts maestros documentados que podrás reusar en tu trabajo real.

> ⏱️ **Tiempo total:** 60 minutos

### 🎯 Objetivo

Crear 3 prompts maestros usando RICE y técnicas avanzadas (Chain of Thought, Few-shot), documentados en un formato que puedas reusar y compartir.

### 🔑 Conceptos Clave

- **RICE**: Rol + Instrucción + Contexto + Ejemplo
- **Chain of Thought**: "Piensa paso a paso antes de responder"
- **Few-shot**: Incluir ejemplos de input → output deseado
- **Anti-ejemplo**: Mostrar qué NO quieres

---

## Parte 1: De Bueno a Extraordinario (15 min)

Observa cómo el mismo prompt evoluciona en 3 niveles.

### 1.1. Nivel 1: El Prompt Casual

Copia y pega en Claude:

```
Escribe un email de seguimiento después de una reunión.
```

**Observa:** ¿Es útil? ¿Lo enviarías tal cual?

### 1.2. Nivel 2: Con Estructura Básica (Clase 01)

```
Actúa como un profesional de negocios.

Trabajo en una agencia de marketing digital y tuve una reunión
con un cliente potencial sobre un proyecto de branding.

Escribe un email de seguimiento post-reunión.

Preséntalo como email listo para enviar con subject line.
```

**Observa:** Mejoró, pero ¿tiene tu tono? ¿Tu contexto específico?

### 1.3. Nivel 3: RICE Completo

```
[ROL]
Eres un consultor senior de marketing con 10 años de experiencia
cerrando clientes corporativos. Tu tono es profesional pero cálido.

[INSTRUCCIÓN]
Escribe un email de seguimiento para enviar 24 horas después
de una reunión de discovery con un cliente potencial.

[CONTEXTO]
- Cliente: Director de Marketing de empresa de tecnología (50-100 empleados)
- Reunión: Discovery de 45 min sobre rebranding
- Pain points mencionados: marca desactualizada, competidores más modernos
- Próximo paso acordado: enviar propuesta en 1 semana
- Mi empresa: Agencia boutique especializada en tech startups

[EJEMPLO de tono deseado]
"Gracias por compartir los desafíos de [Empresa] tan abiertamente.
Es exactamente el tipo de proyecto donde podemos agregar valor..."

[ANTI-EJEMPLO - NO quiero esto]
- Nada genérico tipo "fue un placer conocerlo"
- Nada vendedor/agresivo tipo "no pierda esta oportunidad"
- Nada largo (máximo 150 palabras)
```

**Observa:** ¿Ves la diferencia? El ejemplo y anti-ejemplo eliminan ambigüedad.

### 1.4. Reflexión grupal (3 min)

- ¿Cuál de los 3 usarías en tu trabajo?
- ¿Qué elemento hizo la mayor diferencia?

---

## Parte 2: Prompt Battle (20 min)

### El Reto

Todos van a resolver el **mismo problema** con su propio prompt. Después votamos el mejor.

**Escenario:**
> Tu jefe te pide que resumas un documento técnico de 10 páginas para presentar los puntos clave al CEO en 2 minutos. El CEO odia el tecnicismo y quiere saber: ¿qué significa esto para el negocio?

### 2.1. Escribe tu prompt (8 min)

Usa RICE para crear tu mejor prompt. Puedes usar Claude para iterarlo.

**Tip:** Piensa en:
- ¿Qué rol sería más útil?
- ¿Qué instrucción específica?
- ¿Qué contexto sobre el CEO/empresa?
- ¿Qué ejemplo de formato/tono?

### 2.2. Ejecuta y captura (2 min)

- Ejecuta tu prompt en Claude (usa cualquier texto técnico que tengas o inventa uno)
- Captura screenshot del resultado

### 2.3. Votación (10 min)

**Formato:**
1. 3-4 voluntarios comparten su prompt y resultado (2 min c/u)
2. Votación rápida: ¿cuál funcionó mejor?
3. Discusión: ¿qué hizo que el ganador funcionara?

---

## Parte 3: Mi Prompt de Análisis (15 min)

Ahora crearás tu primer prompt maestro para **analizar información**.

### 3.1. Elige tu tarea de análisis

De las 3 tareas que trajiste, elige una que involucre:
- Analizar datos o información
- Evaluar opciones
- Identificar patrones o problemas
- Tomar decisiones basadas en información

### 3.2. Aplica RICE + Chain of Thought

Usa esta estructura:

```
[ROL]
Eres un [experto relevante] con experiencia en [tu industria].

[INSTRUCCIÓN]
Analiza [qué cosa] y dame [qué resultado].

Antes de dar tu conclusión, piensa paso a paso:
1. Primero identifica [aspecto 1]
2. Luego evalúa [aspecto 2]
3. Considera [aspecto 3]
4. Finalmente, concluye con [recomendación]

[CONTEXTO]
- Mi situación: [describe]
- Lo que ya sé: [información previa]
- Mi objetivo: [qué quiero lograr]
- Restricciones: [límites o condiciones]

[EJEMPLO de output deseado]
"Basado en el análisis:
1. Hallazgo principal: ...
2. Implicación para ti: ...
3. Recomendación: ..."
```

### 3.3. Ejecuta e itera (5 min)

- Prueba tu prompt con información real
- Refina según el resultado
- Guarda la versión final

---

## Parte 4: Mi Prompt Reusable (10 min)

Crearás un segundo prompt maestro usando **Few-shot** para un formato específico.

### 4.1. Elige tu tarea de formato

Elige algo donde necesites un formato consistente:
- Escribir emails de un tipo específico
- Crear resúmenes ejecutivos
- Generar bullets para presentaciones
- Redactar posts o mensajes

### 4.2. Aplica RICE + Few-shot

```
[ROL]
Eres [rol] especializado en [área].

[INSTRUCCIÓN]
Genera [qué cosa] siguiendo exactamente el formato de los ejemplos.

[CONTEXTO]
- Audiencia: [quién lo leerá]
- Tono: [formal/casual/técnico]
- Longitud: [especifica]

[EJEMPLOS]

Ejemplo 1:
Input: [input de ejemplo]
Output: [output exacto que quieres]

Ejemplo 2:
Input: [otro input]
Output: [otro output en el mismo formato]

---

Ahora genera para:
Input: [tu input real]
```

### 4.3. Documenta tu prompt maestro

Guarda con este formato:

```
PROMPT MAESTRO: [Nombre descriptivo]
Uso: [Para qué sirve]
Técnicas: RICE + Few-shot
---
[Tu prompt completo]
---
Resultado esperado: [Qué obtienes]
```

---

## 📝 Entregable

**Para la tarea de esta clase, deberás entregar 3 prompts maestros:**

### Prompt 1: Transformación (de Parte 1 o Battle)
```
Nombre:
Uso:
Técnicas aplicadas: RICE + [otras]
---
[Prompt completo]
---
Screenshot del resultado
```

### Prompt 2: Análisis (de Parte 3)
```
Nombre:
Uso:
Técnicas aplicadas: RICE + Chain of Thought
---
[Prompt completo]
---
Screenshot del resultado
```

### Prompt 3: Formato Reusable (de Parte 4)
```
Nombre:
Uso:
Técnicas aplicadas: RICE + Few-shot
---
[Prompt completo]
---
Screenshot del resultado
```

**Formato de entrega:** Documento de Google con los 3 prompts + screenshots, compartir públicamente y pegar el link como entrega.

---

## 🏆 Retos Adicionales (si terminas antes)

### Reto 1: El Prompt Perfeccionista
- Toma tu mejor prompt y agrega anti-ejemplos
- ¿Mejoró el resultado?

### Reto 2: Combina Técnicas
- Crea un prompt que use Chain of Thought Y Few-shot
- ¿Es más efectivo o demasiado largo?

### Reto 3: El Prompt Universal
- Crea un "meta-prompt" que genere otros prompts
- Input: descripción de tarea → Output: prompt RICE completo

---

## Checklist de Calidad

Antes de entregar, verifica:

- [ ] ¿Cada prompt tiene los 4 elementos de RICE?
- [ ] ¿Incluí al menos un ejemplo de output deseado?
- [ ] ¿Mis prompts son para tareas REALES de mi trabajo?
- [ ] ¿Los screenshots muestran resultados útiles?
- [ ] ¿Podría reusar estos prompts mañana mismo?
