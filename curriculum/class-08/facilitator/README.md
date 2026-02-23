# Guía del Facilitador - Clase 08: Demo Day + El Futuro

> Tiempo de lectura: 12 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Open-source**: Código público que otros pueden ver, estudiar y aprender de él. Los estudiantes publican su primer repo con SystemPrompts documentados.
- **Demo Day**: Sesión de pitches donde cada estudiante presenta su caso en 3 minutos. No es examen — es celebración con evidencia.
- **Accountability**: Compromiso público que motiva a cumplir. Publicar juntos en LinkedIn.
- **NanoBanana**: Estilo de generación de imágenes en Gemini para crear portadas profesionales con logos del stack.

---

## Analogías Útiles

**GitHub = tu portafolio de arquitecto:**
No solo muestras el edificio (Vercel), también los planos (SystemPrompts). Eso es lo que te diferencia.

**LinkedIn post + repo = tarjeta de presentación con evidencia:**
No es publicar por publicar. Es un agente funcionando + código documentado + métricas reales.

**Plan 30 días = programa de entrenamiento:**
No es lista de deseos de Año Nuevo. Son 3 acciones concretas esta semana.

---

## Contexto Pedagógico

Esta es la clase más emocional del curso y la más densa en entregables. Tu rol es **facilitador de confianza + director de tiempo**, no evaluador. Los estudiantes hacen 3 cosas grandes hoy: GitHub, LinkedIn y pitch. Cada bloque tiene su propio checkpoint — no dejes que se alarguen.

### ¿Por qué GitHub se movió a C08?

En C07, el tiempo de construcción del agente (Make + 5 módulos) no dejaba espacio para GitHub. Moviendo GitHub a C08 se logra:
1. Más tiempo en C07 para construir sin prisa
2. En C08, GitHub se conecta naturalmente con LinkedIn (repo = evidencia del post)
3. El flujo Vercel → GitHub es técnicamente simple (5-7 min) pero el README necesita cuidado

### Riesgo principal

Estudiantes atascados en autenticación de GitHub (primera vez). Tener protocolo claro y buffer de 3 min.

---

## Preparación ANTES de Clase

### Crítico

1. **Test M2 en Google Forms** — 8 preguntas listas (ver sección Test)
2. **Tu propio repo en GitHub** con README profesional — lo muestras como ejemplo
3. **Tu propio LinkedIn post** publicado como ejemplo — muéstralo antes de pedir que publiquen
4. **Timer estricto** para pitches (3 min presentación + 30 seg feedback)
5. **Logos SVG verificados** — `curriculum/class-08/lab/assets/` tiene 8 SVGs
6. **Gemini probado** — genera una imagen de ejemplo con los logos para mostrar
7. **Info AI 201/301** para compartir al final
8. **Celebración lista** — aplausos, certificados si hay, cierre digno

---

## Estructura de la Clase — 5 Bloques (~150 min)

### BLOQUE 1: Apertura + Test (~30 min)

#### Pregunta Detonadora (~3 min)

**Respuesta correcta: C** — Métricas reales + demo funcionando + repo público

**Script post-votación:**
```
"Cualquiera puede decir 'uso IA'. La diferencia está en DEMOSTRAR.
Un agente que funciona + métricas + un repo en GitHub con tus SystemPrompts
es más poderoso que cualquier narrativa.
Hoy construyen la evidencia completa."
```

#### Test Diagnóstico M2 (~15 min)

**Script para introducir:**
```
"Antes de empezar, un test rápido.
8 preguntas, 15 minutos. No afecta calificación.
Es un espejo — les muestra qué conceptos dominan
y cuáles necesitan más práctica."
```

| # | Clase | Tema | Respuesta |
|---|-------|------|-----------|
| 1 | C05 | Diferencia automatización vs agente | B — IA decide, no solo ejecuta reglas |
| 2 | C05 | Qué define calidad del agente | C — SystemPrompt con categorías y reglas claras |
| 3 | C06 | Qué es Router en Make | B — Divide flujo en rutas condicionales |
| 4 | C06 | Para qué logging (Sheets) | C — Auditar decisiones y mejorar con datos |
| 5 | C07 | Al transferir a tu caso, qué cambia | B — SystemPrompt + categorías + reglas + form |
| 6 | C07 | Agente clasifica todo igual, qué arreglar | A — Reglas del SystemPrompt |
| 7 | Integración | Agente profesional completo necesita | D — Cerebro + acciones + logging + supervisión |
| 8 | Auto | Confianza para integrar IA | Sin respuesta correcta |

Ver `test/questions.md` para preguntas completas con opciones y justificaciones.

#### Retrospectiva C01→C07 (~12 min)

**Script:**
```
"Hace 4 semanas pensaban que la IA era Google mejorado.
Vamos a recorrer lo que pasó."
```

Recorrido guiado (2 min por módulo):

**Módulo 1 (C01-C04):**
- "C01: descubrieron que la IA no es magia — necesita instrucciones claras"
- "C02: aprendieron RICE y Few-shot — el prompt pasó de genérico a profesional"
- "C03: Claude dejó de ser asistente y se volvió socio pensante"
- "C04: integraron todo en un proyecto real con Gemini y Perplexity"

**Módulo 2 (C05-C07):**
- "C05: construyeron el cerebro de un agente — SystemPrompt + categorías"
- "C06: el agente tomó decisiones solo — Router + Sheets"
- "C07: diseñaron su PROPIO agente con 2 IAs encadenadas"
- "Hoy: lo publican como proyecto open-source"

**Pregunta al grupo:** "¿Cuál fue el momento donde más se frustraron? ¿Y cuál fue el momento WOW?"

> **Checkpoint ~min 30:** Retrospectiva completada, energía del grupo alta

---

### BLOQUE 2: GitHub — Mi Primer Proyecto Open-Source (~30 min)

#### Intro facilitador (~2 min)

Muestra TU repo como ejemplo:
```
"Este es mi repo. Tiene el código del form, el README con mis SystemPrompts,
y la URL de demo. Cualquiera puede ver cómo funciona mi agente.
Esto es lo que van a crear en los próximos 25 minutos."
```

#### Conectar Vercel → GitHub (~7 min)

1. Guía paso a paso: vercel.com → Settings → Git → Connect to GitHub → autorizar
2. Vercel crea el repo automáticamente

**Errores comunes:**
| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "GitHub me pide autenticar" | Primera vez usando GitHub | Ayudar con OAuth flow — crear cuenta si es necesario |
| "Vercel no conecta" | Permisos de la app | Settings de GitHub → Applications → autorizar Vercel |
| "No veo mi proyecto en Vercel" | Login incorrecto | Verificar que usan la misma cuenta de Vercel que en C07 |

#### README completo en GitHub web (~13 min)

- Desde github.com → abrir repo → editar README.md → ícono de lápiz
- Copiar estructura del lab (nombre, arquitectura, SystemPrompts, ejemplo, URL)
- **Asegurar que peguen ambos SystemPrompts completos** — es la pieza intelectual del proyecto
- Commit desde el navegador

**Momento WOW:**
```
"Miren su repo. Eso es open-source.
Cualquiera puede ver cómo funciona tu agente.
Los SystemPrompts son la propiedad intelectual de tu proyecto."
```

#### Verificar repo público (~5 min)

- Verificar que el repo es público (si es privado → Settings → Change Visibility)
- Verificar que el README se renderiza correctamente

#### Buffer técnico (~3 min)

Tiempo extra para problemas de auth/cuenta. Si nadie lo necesita, avanzar.

> **Checkpoint ~min 60:** "¿Quién tiene repo público con README?" — Manos arriba.

---

### BLOQUE 3: Preparar LinkedIn + Imagen (~30 min)

#### Draft con Claude (~10 min)

- Template del lab: problema + solución + URLs + métrica + takeaway
- Iterar al menos 1 vez con Claude
- **Clave:** que incluyan AMBAS URLs (Vercel + GitHub)

**Script:**
```
"El post tiene 5 partes: hook, qué construiste, las URLs,
un resultado real y un aprendizaje honesto.
Claude les ayuda con el texto, pero la métrica y la honestidad son suyas."
```

#### Imagen con Gemini (~10 min)

- Logos disponibles en `class-08/lab/assets/`: 8 SVGs del stack
- Los estudiantes descargan 3-4 logos relevantes
- Suben a Gemini + prompt descriptivo → imagen de portada

**Si la generación de imagen no funciona bien:**
- Alternativa: usar Canva con los logos como fallback
- O simplemente publicar sin imagen — el contenido es lo que importa

#### Peer review en parejas (~10 min)

- Intercambiar posts
- Feedback específico: hook, métrica, URLs, tono
- Ajustar con feedback

> **Checkpoint ~min 90:** "¿Quién tiene post listo + imagen?" — Manos arriba.

---

### BLOQUE 4: Pitches + Publicar (~30 min)

#### Pitches — 3 min c/u (~25 min)

**Script para iniciar:**
```
"Hoy no presentan slides. Proyectan su post de LinkedIn.
Explican el problema. Muestran el agente.
3 minutos. Vamos."
```

**Protocolo por pitch:**
1. Presentador proyecta su post de LinkedIn (2 min)
   - Explica el problema que resuelve
   - Muestra URLs (Vercel + GitHub)
2. Demo rápida (1 min)
   - Alguien del público envía mensaje al form
   - Todos ven el email llegar
3. Feedback rápido del grupo (~30 seg)
   - "Lo más fuerte de tu pitch fue..."

**Manejo de tiempo para pitches:**

| Tamaño grupo | Por persona | Total estimado | Ajuste |
|--------------|-------------|----------------|--------|
| 6-8 personas | 3 min + 30 seg = ~3.5 min | 21-28 min | Formato estándar |
| 9-12 personas | 2 min + 30 seg = ~2.5 min | 23-30 min | Demo opcional |
| 13+ personas | 2 min pitch only | 26+ min | Sin demo individual, 2-3 demos grupales |

**Si el agente falla en vivo:**
```
"Eso pasa. La demo en vivo es impredecible.
¿Tienes un run exitoso en Make History? Muéstralo.
Lo importante: sabes diagnosticar qué pasó."
```

**Herramientas de control de tiempo:**
- Timer visible para todos
- Tarjeta "30 segundos" cuando queda poco
- Cortar con amabilidad: "Gracias, pasemos al siguiente"

#### "3... 2... 1... PUBLICAR!" (~5 min)

**Script:**
```
"¿Todos tienen su post listo? ¿Imagen de portada?
¿LinkedIn abierta?
Lo publicamos juntos. En 3... 2... 1... ¡PUBLICAR!"
[Pausa — dejar que publiquen]
"Screenshot. Ese post tiene un agente FUNCIONANDO
y un repo en GitHub detrás. Eso es más de lo que puede
mostrar el 99% de la gente."
```

**Si alguien duda:**
```
"Tu post tiene evidencia real: un agente que funciona,
un repo con SystemPrompts, y una métrica de tu trabajo.
No es hype. Es evidencia. Publícalo."
```

> **Checkpoint ~min 120:** "¿Quién publicó?" — Screenshot grupal.

---

### BLOQUE 5: Cierre del Curso (~30 min)

#### Roadmap 30 días con Claude (~15 min)

- Template del lab: plan por semana + 3 quick-wins
- Cada persona comparte su quick-win #1 (1 oración)
- Facilitador anota en pantalla los más creativos

**Script:**
```
"El curso termina hoy. Tu desarrollo no.
Claude les va a ayudar a crear un plan concreto.
No 30 metas. 3 acciones ESTA SEMANA."
```

#### Anti-Hype + Pathway (~5 min)

**Script:**
```
"4 verdades antes de cerrar:
1. 4 semanas = inicio, no final.
2. Las herramientas van a cambiar. El pensamiento crítico con IA no.
3. Publicar en LinkedIn no te hace experto. La práctica continua sí.
4. Tu agente necesita supervisión. Ninguna IA reemplaza el criterio humano."
```

**Pathway:**
- AI 201 — Construir con IA (para quienes quieren crear soluciones)
- AI 301 — Escalar con IA (para quienes quieren producto/startup)

#### Cierre emocional (~10 min)

**Script sugerido:**
```
"Hace 4 semanas, muchos pensaban que la IA era un Google mejorado.
Hoy tienen un agente que funciona para SU trabajo.
Un proyecto open-source en GitHub.
Evidencia publicada en LinkedIn.
Un plan para seguir.

Pasaron del 95% al 5%.

Las herramientas van a cambiar — Make puede ser reemplazado,
nuevos modelos van a aparecer cada mes.
Pero lo que aprendieron — pensar críticamente con IA,
diseñar sistemas, iterar con datos, comunicar resultados —
eso no caduca.

Gracias por estas 4 semanas."
```

> **Checkpoint ~min 150:** Cierre emocional completado. Momento de celebración.

---

## Errores Esperados

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "GitHub me pide autenticar" | Primera vez usando GitHub | Ayudar con OAuth flow |
| "Vercel no conecta a GitHub" | Permisos de la app | Settings → Applications → autorizar Vercel |
| "No sé qué poner en el README" | Parálisis de página en blanco | "Copia la estructura del lab. Solo llena los espacios" |
| "Gemini no genera buena imagen" | Prompt poco específico | Ajustar prompt o usar Canva como fallback |
| Sin métricas reales | No midió antes/después | "¿Cuánto te tomaba ANTES? ¿Y AHORA con el agente?" |
| Miedo a publicar en LinkedIn | Síndrome del impostor | "Tu post tiene repo + agente. Más que el 99%" |
| Pitch muy largo | Se extiende en explicaciones | Timer estricto + tarjeta "30 segundos" |
| No terminó agente C07 | No preparó | "Muestra agente PetShop de C06. Explica qué SERÍA tu caso" |
| No quiere presentar | Ansiedad | "Puedes solo mostrar tu post y hacer la demo" |

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~3 | PD votada | Discusión sobre credibilidad completada |
| ~18 | Test M2 completado | Todos enviaron respuestas en Forms |
| ~30 | Retrospectiva completada | Energía del grupo alta |
| ~60 | Repo público + README | "¿Quién tiene repo con SystemPrompts?" |
| ~90 | Post LinkedIn + imagen | "¿Quién tiene post listo?" |
| ~120 | Pitches + LinkedIn publicado | "¿Quién publicó? Screenshot!" |
| ~135 | Roadmap creado | "¿Quién tiene 3 quick-wins?" |
| ~150 | Cierre emocional | Momento de celebración grupal |

---

## Tips de Facilitación

### Para GitHub:
- "Solo vas a editar un archivo de texto en una página web. No necesitas saber programar."
- Mostrar en tu pantalla cómo se edita un README en GitHub web
- Si realmente no pueden: que documenten SystemPrompts en un Google Doc como backup
- Los ~3 min de buffer técnico son para problemas de auth — no los uses para otra cosa

### Para LinkedIn + Imagen:
- Mostrar TU propio post primero como ejemplo
- La imagen de Gemini es un bonus — si no sale bien, publicar sin imagen está bien
- Publicar JUNTOS reduce la ansiedad individual
- No forzar — si alguien prefiere publicar después, está bien. Pero el momento grupal es poderoso

### Para los pitches:
- Timer estricto es no-negociable. Sin timer, los pitches se extienden
- Iniciar con alguien confiado para establecer el tono
- El post de LinkedIn ES la presentación — no necesitan slides extra
- Aplaudir genuinamente después de cada pitch

### Para el cierre:
- No apures el cierre emocional. Son 10 minutos que importan
- Menciona algo específico de cada estudiante si es grupo pequeño
- Comparte info de AI 201/301 como siguiente paso natural

```
"El mejor indicador de que AI 101 funcionó:
¿siguen usando lo que aprendieron 30 días después?"
```
