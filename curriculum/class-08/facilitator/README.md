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

**Respuesta correcta: C** — Métricas reales + demo funcionando + repo público. Mensaje clave: "Cualquiera puede decir 'uso IA'. La diferencia está en DEMOSTRAR."

#### Test Diagnóstico M2 (~15 min)

8 preguntas, 15 minutos. No afecta calificación — es un espejo de comprensión. Respuestas: 1-B, 2-C, 3-B, 4-C, 5-B, 6-A, 7-D, 8-sin correcta. Ver `test/questions.md` para preguntas completas.

#### Retrospectiva C01→C07 (~12 min)

Recorrido rápido (2 min por módulo). Usa las slides como apoyo visual:
- **M1:** Instrucciones claras (C01) → RICE + Few-shot (C02) → Socio pensante (C03) → Proyecto integrador (C04)
- **M2:** Cerebro del agente (C05) → Router + Sheets (C06) → Agente propio con 2 IAs (C07) → Hoy: open-source

**Pregunta al grupo:** "¿Cuál fue el momento donde más se frustraron? ¿Y cuál fue el momento WOW?"

> **Checkpoint ~min 30:** Retrospectiva completada, energía del grupo alta

---

### BLOQUE 2: GitHub — Mi Primer Proyecto Open-Source (~30 min)

#### Intro facilitador (~2 min)
Muestra TU repo como ejemplo — código del form, README con SystemPrompts, URL de demo.

#### Conectar Vercel → GitHub (~7 min)
Guía: vercel.com → Settings → Git → Connect to GitHub → autorizar. Vercel crea el repo automáticamente.

Errores comunes: auth de GitHub (ayudar con OAuth), permisos (Settings → Applications → autorizar Vercel), login incorrecto (verificar misma cuenta de C07).

#### README completo en GitHub web (~13 min)
- github.com → repo → editar README.md → estructura del lab → **pegar ambos SystemPrompts** → commit
- Verificar repo público (Settings → Change Visibility si es privado)

#### Buffer técnico (~3 min)
Para problemas de auth/cuenta. Si nadie lo necesita, avanzar.

> **Checkpoint ~min 60:** "¿Quién tiene repo público con README?" — Manos arriba.

---

### BLOQUE 3: Preparar LinkedIn + Imagen (~30 min)

#### Draft con Claude (~10 min)
- Template del lab: problema + solución + URLs + métrica + takeaway
- **Clave:** que incluyan AMBAS URLs (Vercel + GitHub)

#### Imagen con Gemini (~10 min)
- Logos en `class-08/lab/assets/` (8 SVGs). Descargan 3-4 → suben a Gemini → imagen portada
- Fallback: Canva con logos, o publicar sin imagen

#### Peer review en parejas (~10 min)
- Intercambiar posts → feedback: hook, métrica, URLs, tono → ajustar

> **Checkpoint ~min 90:** "¿Quién tiene post listo + imagen?" — Manos arriba.

---

### BLOQUE 4: Pitches + Publicar (~30 min)

#### Pitches — 3 min c/u (~25 min)

Protocolo por pitch: post LinkedIn (2 min) → demo rápida (1 min) → feedback grupal (30 seg). Ver lab para protocolo detallado.

**Control de tiempo:** Timer visible + tarjeta "30 seg" + cortar con amabilidad. Grupos 9+: demo opcional. Grupos 13+: 2 min sin demo individual.

**Si el agente falla en vivo:** "¿Tienes un run exitoso en Make History? Muéstralo. Sabes diagnosticar qué pasó."

#### "3... 2... 1... PUBLICAR!" (~5 min)

Todos publican juntos. El momento grupal reduce la barrera. Si alguien duda: "Tu post tiene evidencia real — un agente funcionando y un repo. Publícalo."

> **Checkpoint ~min 120:** "¿Quién publicó?" — Screenshot grupal.

---

### BLOQUE 5: Cierre del Curso (~30 min)

#### Roadmap 30 días con Claude (~15 min)
- Template del lab: plan por semana + 3 quick-wins. Cada persona comparte quick-win #1 (1 oración)

#### Anti-Hype + Pathway (~5 min)
4 verdades: (1) 4 semanas = inicio, no final. (2) Herramientas cambian, pensamiento crítico no. (3) LinkedIn no te hace experto, la práctica sí. (4) Tu agente necesita supervisión.

**Pathway:** AI 201 (Construir con IA) → AI 301 (Escalar con IA)

#### Cierre emocional (~10 min)
Mensaje central: "Pasaron del 95% al 5%. Herramientas van a cambiar. Pensar críticamente con IA, diseñar sistemas, iterar con datos — eso no caduca."

> **Checkpoint ~min 150:** Cierre emocional completado. Momento de celebración.

---

## Errores Esperados

| Señal | Qué hacer |
|-------|-----------|
| GitHub auth falla | Ayudar con OAuth flow. Buffer técnico de 3 min |
| "No sé qué poner en el README" | "Copia la estructura del lab. Solo llena los espacios" |
| Sin métricas reales | "¿Cuánto te tomaba ANTES? ¿Y AHORA con el agente?" |
| Miedo a publicar en LinkedIn | "Tu post tiene repo + agente. Más que el 99%" |
| No terminó agente C07 | "Muestra PetShop de C06. Explica qué SERÍA tu caso" |

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

## ✅ Señales de Comprensión

**ENTIENDE cuando:**
- Puede explicar por qué su repo + URL + métrica es más valioso que un certificado
- Su pitch se enfoca en el problema que resuelve, no en las herramientas que usó

**NECESITA AYUDA cuando:**
- Su post de LinkedIn es solo descripción de herramientas sin resultado concreto
- No puede articular qué problema resuelve su agente en 1 oración

---

## 🔀 Diferenciación

**Estudiantes avanzados:** Que ayuden a compañeros con GitHub auth, que agreguen sección "Aprendizajes" al README, que comenten posts de LinkedIn de sus compañeros.

**Estudiantes con dificultades:** Que documenten SystemPrompts en Google Doc si GitHub no funciona, que usen el agente PetShop de C06 como base para el pitch.

---

## 🎭 Dinámicas de Clase

### "El Elevator Pitch"
```
Facilitador: "En 30 segundos: ¿qué problema resuelve tu agente?"
[Cada persona responde en 1 oración. Si tarda más de 30 seg, cortar]
"Si no puedes decirlo en 30 segundos, tu pitch de 3 min no va a funcionar."
```

---

## 💡 Ejemplos Listos para Usar

### Template README para GitHub:
```
# [Nombre del Agente]
[1 línea: qué hace]

## Arquitectura
Form → Webhook → OR#1 (analiza) → Sheets → OR#2 (genera) → Gmail

## SystemPrompts
### OR#1 — Analizar
[pegar SystemPrompt]

### OR#2 — Generar
[pegar SystemPrompt]

## Demo
[URL de Vercel]
```

---

## ❓ Preguntas Frecuentes

### "¿Tengo que publicar en LinkedIn?"
No es obligatorio, pero el momento grupal reduce la barrera. Puedes publicar después si prefieres.

### "¿Mi repo tiene que ser público?"
Para este ejercicio sí — es la pieza de portfolio. No contiene datos sensibles (solo SystemPrompts y código de form).

---

## 🪞 Reflexión Post-Clase

1. **¿El cierre emocional aterrizó?** — Si el grupo estaba distraído, puede que fue muy largo.
2. **¿Cuántos publicaron en LinkedIn?** — Meta: >70% del grupo.
3. **¿Los pitches fueron de calidad?** — Si la mayoría describió herramientas en vez de problemas, reforzar para futuros cohorts.
4. **¿El curso logró el cambio de mindset "del 95% al 5%"?** — Revisar test M2 para evidencia.

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
