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

Abre Claude y usa este prompt:

```
Ayúdame a escribir un post de LinkedIn sobre mi primer proyecto
open-source con IA. Datos:
- Problema: [qué me costaba en mi trabajo]
- Solución: agente IA con 2 cerebros encadenados (analiza + genera)
- Herramientas: Make + OpenRouter + Gemini Flash + Gmail + Sheets
- URL del agente: [tu URL de Vercel]
- Repo con SystemPrompts: [tu URL de GitHub]
- Métrica: [resultado real — ej: "procesé 10 notas de reunión"]
- Limitación honesta: [qué no hace bien tu agente]

Formato: Hook (1 línea) + Qué construí (2-3 líneas) + URLs + Resultado + Takeaway
Tono: profesional pero accesible. Sin hype.
```

Itera al menos 1 vez. El post debe tener:
- Hook que capture atención (1 línea)
- Descripción de lo que construiste (2-3 líneas)
- URLs: Vercel + GitHub
- Métrica real
- Aprendizaje honesto

### 2.2 Imagen de portada con Gemini (10 min)

1. Toma un **screenshot** de este grid de logos (tu stack tecnológico):

<style>
.stack-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;max-width:520px;padding:24px;background:#0A192F;border-radius:12px;margin:16px 0}
.stack-grid .logo-card{background:#1A2744;border:1px solid #2D3F5E;border-radius:10px;padding:14px 8px;text-align:center}
.stack-grid .logo-card img{width:40px;height:40px;margin-bottom:6px}
.stack-grid .logo-card span{display:block;color:#94A3B8;font-size:0.75rem;font-family:sans-serif}
</style>

<div class="stack-grid">
  <div class="logo-card"><img src="assets/claude.svg" alt="Claude"><span>Claude</span></div>
  <div class="logo-card"><img src="assets/gemini.svg" alt="Gemini"><span>Gemini</span></div>
  <div class="logo-card"><img src="assets/github.svg" alt="GitHub"><span>GitHub</span></div>
  <div class="logo-card"><img src="assets/make.svg" alt="Make"><span>Make</span></div>
  <div class="logo-card"><img src="assets/openrouter.svg" alt="OpenRouter"><span>OpenRouter</span></div>
  <div class="logo-card"><img src="assets/v0.svg" alt="v0"><span>v0</span></div>
  <div class="logo-card"><img src="assets/drive.svg" alt="Drive"><span>Drive</span></div>
  <div class="logo-card"><img src="assets/gmail.svg" alt="Gmail"><span>Gmail</span></div>
</div>

2. Abre **Gemini** → sube el screenshot + usa este prompt:

```
Genera una imagen con los logos de la imagen adjunta.
Estilo: íconos 3D tipo app icons con volumen y sombras suaves,
colocados sobre una base de vidrio transparente con efecto glassmorphism,
en perspectiva isométrica. Líneas sutiles de conexión tipo network
entre los íconos, con el ícono central más grande y prominente. El ícono central debe ser "Claude".
Atmósfera futurista, limpia y profesional. Calidad 8k, renderizado en Octane, estilo visual de interfaz de usuario de última generación (Next-gen UI). Sin texto adicional, solo el impacto visual de las marcas integradas en un ecosistema digital colaborativo.
Fondo oscuro con degradado azul-púrpura.
Formato horizontal, ideal para banner de LinkedIn.
Todos los logos deben verse bien desde la perspectiva de un observador que está en la esquina inferior derecha.
```

3. Descarga la imagen generada

> 💡 **Tip:** Si la primera imagen no convence, itera: "más contraste entre íconos", "fondo más oscuro", "líneas de conexión más visibles".

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

Abre Claude y usa este prompt:

```
Construí un agente generativo que [describe tu caso] usando
Make + OpenRouter (2 IAs encadenadas) + Gmail + Google Sheets.
Publiqué el proyecto en GitHub y LinkedIn.

Ayúdame a crear un plan de 30 días:
- Semana 1: Mejorar calidad del agente actual (SystemPrompts + casos edge)
- Semana 2: Expandir a más casos o inputs diferentes
- Semana 3: Aplicar el patrón a otro proceso de mi trabajo
- Semana 4: Medir impacto real y documentar resultados

Dame 3 quick-wins que pueda hacer ESTA SEMANA.
```

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

## Bonus (opcional)

- Agrega un badge de "Built with AI" al README de GitHub
- Comenta en el post de LinkedIn de al menos 2 compañeros
- Envía tu repo al facilitador para incluirlo en un showcase del curso
- Mejora la imagen de portada con iteraciones en Gemini
