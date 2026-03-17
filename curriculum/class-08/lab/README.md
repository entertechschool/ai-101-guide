# Lab 08: Mi Proyecto Open-Source

## Objetivo

Publicar tu agente como proyecto open-source en GitHub, crear un post de LinkedIn con imagen generada por IA, presentar tu caso en un pitch de 3 minutos y crear un plan de desarrollo para los próximos 30 días.

> ⏱️ **Tiempo estimado:** 100 minutos (sin contar test ni retrospectiva previa)

---

## Antes de empezar

| ✅ | Requisito |
|----|-----------|
| | Agente C07 funcionando (URL Vercel activa + Make encendido) |
| | Cuenta de GitHub creada |
| | SystemPrompts (OR#1 + OR#2) copiados y accesibles |
| | Cuenta de LinkedIn abierta |
| | Cuenta de Gemini abierta |

### Test Diagnóstico M2 (15 min, pre-lab)

- 8 preguntas de opción múltiple
- No afecta calificación — **"es un espejo, no un examen"**
- El facilitador comparte el link (Google Forms)
- Individual, sin consultar materiales

> ✅ **Checkpoint:** Test completado

---

## Parte 1: GitHub — Mi Primer Proyecto Open-Source (25 min)

### 1.1 Conectar Vercel → GitHub (7 min)

1. Abre **vercel.com** → busca tu proyecto (el form de C07)
2. Ve a **Settings** → **Git**
3. Click **"Connect to GitHub"** → autoriza tu cuenta de GitHub
4. Vercel crea un repositorio automáticamente con el código de tu form
5. Verifica: abre github.com → deberías ver un nuevo repo

> 💡 **No necesitas terminal ni CLI.** Todo se hace desde la interfaz web de Vercel/GitHub.

> ⚠️ **Si GitHub pide autorizar:** Es normal la primera vez. Acepta los permisos de la app de Vercel.

### 1.2 Editar README en GitHub web (13 min)

Desde github.com, abre tu repo → click en el archivo `README.md` → click el ícono de lápiz (editar).

Reemplaza el contenido con esta estructura:

```markdown
# [Nombre de tu proyecto]

## Qué hace
[1-2 oraciones describiendo qué problema resuelve tu agente]

## Arquitectura
Form (Vercel) → Webhook (Make) → OpenRouter #1 (analizar) → Sheets (log) → OpenRouter #2 (generar) → Gmail

## SystemPrompt #1 — Analizar
[Pega tu SystemPrompt completo de OR#1]

## SystemPrompt #2 — Generar
[Pega tu SystemPrompt completo de OR#2]

## Ejemplo
**Input:** [Un ejemplo real de lo que escribes en el form]
**Output:** [Resumen de lo que llega al email]

## Herramientas
- v0 + Vercel (form + hosting)
- Make (orquestación)
- OpenRouter + Gemini Flash (IA)
- Google Sheets (logging)
- Gmail (envío)

## Demo
[URL de tu form en Vercel]
```

Commit desde el navegador (botón "Commit changes").

### 1.3 Verificar repo público (5 min)

| ✅ | Verificación |
|----|-------------|
| | Repo visible en github.com |
| | README tiene SystemPrompts documentados |
| | URL de demo (Vercel) incluida en el README |

> ⚠️ **Si el repo es privado:** Settings → Danger Zone → Change Visibility → Public

> ✅ **Checkpoint Parte 1:** Repo público en GitHub con README profesional

---

## Parte 2: LinkedIn + Imagen (30 min)

### 2.1 Draft del post con Claude (10 min)

Abre Claude con un prompt que incluya: problema que resuelves, herramientas usadas, URL de Vercel, URL de GitHub, métrica real, limitación honesta. Pide formato: Hook (1 línea) + Qué construí + URLs + Resultado + Takeaway. Tono profesional sin hype.

Itera al menos 1 vez. El post debe tener hook, descripción, URLs (Vercel + GitHub), métrica real y aprendizaje honesto.

### 2.2 Imagen de portada con Gemini (10 min)

1. Toma un **screenshot** del grid de logos de tu stack (en `assets/`: Claude, Gemini, GitHub, Make, OpenRouter, v0, Drive, Gmail)
2. Abre **Gemini** → sube el screenshot + pide: "Genera una imagen con estos logos en estilo 3D glassmorphism isométrico, fondo oscuro azul-púrpura, formato horizontal para banner de LinkedIn"
3. Descarga la imagen. Si no convence, itera: "más contraste", "fondo más oscuro"

### 2.3 Peer review en parejas (10 min)

1. Intercambia tu draft de LinkedIn con un compañero
2. Cada persona da feedback específico:
   - "El hook funciona / no funciona porque..."
   - "Agregaría / quitaría..."
   - "La métrica es clara / necesita más contexto"
3. Ajusta tu post con el feedback recibido

> ✅ **Checkpoint Parte 2:** Post de LinkedIn listo + imagen de portada generada

---

## Parte 3: Pitches + Publicar (30 min)

### 3.1 Pitches — 3 minutos cada uno (~25 min)

**Formato por persona:**

| Bloque | Tiempo | Qué haces |
|--------|--------|-----------|
| **Problema + Post** | 2 min | Proyecta tu post de LinkedIn, explica el problema que resuelve tu agente |
| **Demo rápida** | 1 min | Alguien del público envía un mensaje a tu form → ven el resultado |

**Tips:**
- Proyecta tu post de LinkedIn en pantalla — ES tu presentación
- No expliques cada módulo de Make — enfócate en el problema y el resultado
- La demo es rápida: alguien envía → todos ven el email llegar

> ⚠️ **Si tu demo falla en vivo:** Muestra Make History con un run exitoso anterior (máx 30 seg extra).

### 3.2 "3... 2... 1... PUBLICAR!" (5 min)

1. Agrega la imagen de portada a tu post de LinkedIn
2. El facilitador cuenta: **"3... 2... 1... ¡PUBLICAR!"**
3. Todos publican al mismo tiempo
4. Screenshot del post publicado

> ✅ **Checkpoint Parte 3:** Post de LinkedIn publicado con imagen + URLs

---

## Parte 4: Roadmap 30 Días (15 min)

### 4.1 Plan con Claude (10 min)

Pide a Claude un plan de 30 días para tu agente: Semana 1 (mejorar calidad), Semana 2 (expandir casos), Semana 3 (aplicar a otro proceso), Semana 4 (medir impacto). Incluye 3 quick-wins para esta semana.

### 4.2 Compartir quick-wins (5 min)

- Cada persona comparte su quick-win #1 con el grupo (1 oración)
- El facilitador anota en pantalla los más creativos

> ✅ **Checkpoint Parte 4:** Plan de 30 días + 3 quick-wins concretos

---

## Entregable final

1. **URL de GitHub** — repo público con README que documenta SystemPrompts
2. **LinkedIn post publicado** — con imagen de portada + URLs (Vercel + GitHub)
3. **Plan 30 días** — con 3 quick-wins para esta semana

**Formato:** Links directos (GitHub + LinkedIn) + screenshot del post publicado

---

## Criterios de Evaluación

| Criterio | Peso | Qué se evalúa |
|----------|------|---------------|
| **Repo GitHub** | 20% | ¿Es público, tiene README con SystemPrompts documentados y URL de demo? |
| **Post LinkedIn** | 20% | ¿Tiene hook, descripción, URLs, métrica real y aprendizaje honesto? |
| **Pitch** | 20% | ¿Explicó problema + demo en 3 min? ¿El agente funcionó en vivo? |
| **Imagen generada** | 20% | ¿Usó Gemini para crear imagen de portada? ¿Iteró al menos 1 vez? |
| **Plan 30 días** | 20% | ¿Tiene roadmap semanal + 3 quick-wins concretos? |

---

## Bonus (opcional)

- Agrega un badge de "Built with AI" al README de GitHub
- Comenta en el post de LinkedIn de al menos 2 compañeros
- Envía tu repo al facilitador para incluirlo en un showcase del curso
- Mejora la imagen de portada con iteraciones en Gemini
