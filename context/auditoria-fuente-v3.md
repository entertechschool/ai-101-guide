# Auditoría — Fuente nueva (v3) vs Curriculum actual (v2)

> **Fecha:** 2026-06-03
> **Objetivo:** Determinar a qué clases y artefactos afecta el material fuente nuevo del instructor (`fuente/`) antes de editar el curriculum.
> **Conclusión corta:** No es un ajuste menor. Los *conceptos* se reciclan en ~70%, pero el **empaque cambia casi por completo** (duración, orden de sesiones, caso guía, evaluación, salida de Gems). **Las 8 clases + el README se ven afectados.**

---

## 1. Fuentes auditadas

Carpeta `fuente/` (versionada en el repo, a diferencia de `dev/` que está en `.gitignore`):

| Archivo | Contenido |
|---------|-----------|
| `silabo-ai-v3.docx` | Sílabo v3 — Junio 2026 (datos generales, evaluación, estructura de sesión, las 8 sesiones) |
| `silabo-8sesiones-v3.xlsx` | Malla de 8 sesiones (capacidad, objetivo MINEDU, fundamentos, mini-proyecto). **Consistente con el .docx** |
| `sesion01-prompts-efectivos.pptx` … `sesion08-exposicion.pptx` | 8 presentaciones, ~8-11 slides c/u. Contenido a reflejar **casi tal cual** en `curriculum/class-XX/slides/` |

> `dev/nuevo_silabus_walter/` es la fuente **vieja** (ya usada en una actualización anterior). **No usar.**

---

## 2. Cambios globales (afectan a las 8 clases + README.md raíz)

| Aspecto | Actual (v2) | Fuente nueva (v3) | Severidad |
|---------|-------------|-------------------|-----------|
| **Nombre del curso** | AI 101 — IA estratégica para Profesionales | IA + Automatización No-Code para Profesionales | Media |
| **Duración** | 8 × **2.5h** = 20h | 8 × **60 min** = 8h | 🔴 Crítica |
| **Estructura de sesión** | 80% laboratorio | Apertura 10' · Teoría/Fundamentos 20' · Mini-proyecto 25' · Cierre 5' | 🔴 Alta |
| **Evaluación** | Ponderada (40% entregables / 20% participación / 15% lab M1 / 10% sistema propio / 15% Demo). Entregables post-clase | **En clase: 0 (no hizo) / 100 (sí hizo). SIN entregables post-clase.** Proyecto integrador (S7) + Demo Day (S8). Asistencia + participación en Apertura/Cierre | 🔴 Alta |
| **Caso guía** | **Roberto** (ventas, 3-4 vendedores, reporte de los viernes) | **Facturas** (Drive → registro → IA extrae proveedor → reporte mensual). Roberto/ventas sobrevive solo como mini-proyecto de S4 | 🔴 Alta |
| **Gems** | Presente en S1–S8 (asistente del curso con archivos) | **Eliminado por completo** | 🔴 Alta |
| **Marco MINEDU** | Implícito | Objetivos de aprendizaje MINEDU explícitos por sesión | Media |
| **Nuevos temas** | — | OAuth, Google Cloud Project (Client ID + Secret), Routers, Manejo de errores/notificaciones | Media |

### Huella en el curriculum actual (ocurrencias por archivo)

- **Roberto** → 23 archivos · **Gems** → 22 · **"2.5h / 2.5 horas"** → 11 · **ventas/vendedor** → 35 · **factura** → solo 5

Esto cuantifica el trabajo: hay que purgar Roberto/ventas/Gems/2.5h y sembrar el caso facturas/60-min en casi todos los artefactos.

---

## 3. Reordenamiento de sesiones (mapa v2 → v3)

| # | Actual (v2) | Fuente nueva (v3) | ¿De dónde viene el tema en v2? |
|---|-------------|-------------------|-------------------------------|
| 1 | Prompts y Gems | **Prompts efectivos** (sin Gems) | Mismo lugar (recortado) |
| 2 | Google Sheets con IA | **Make 101 + Google Cloud** | Make venía en S4 (+ OAuth/Cloud nuevo) |
| 3 | Google Slides con IA | **API key de Gemini** | API venía en S5 |
| 4 | Make básico | **JSON + Parse JSON + Variables** | Parse JSON era parte de S5 |
| 5 | Gemini API + 2 flujos | **Plantillas con placeholders** | Slides/plantillas venía en S3 (+ Docs nuevo) |
| 6 | Integración total | **Flujo end-to-end robusto** | Parcial: "mejores prácticas/errores" estaban en S6 |
| 7 | Tu proyecto propio | **Proyecto integrador** | Mismo lugar |
| 8 | Demo Day + ROI | **Exposición / Demo Day** | Mismo lugar |

> Casi nada de material se pierde: **se reordena y se recorta a 60 min**. Google Sheets ya no tiene sesión propia (se absorbe en S2/S4); Google Slides se mueve a S5 y se generaliza a "plantillas Docs/Slides".

---

## 4. Impacto por clase

Severidad: 🟢 Alinear (cambio menor) · 🟡 Ajustar (medio) · 🟠 Rehacer parcial · 🔴 Reemplazar tema

### Clase 1 — Prompts efectivos · 🟡 Ajustar
- **v3 (10 slides):** Portada · Encuadre · Apertura (3 preguntas) · F1 ¿Qué es un prompt? · F2 Anatomía **Rol + Tarea + Contexto + Formato** · Ejemplo real (correo clasificado) · F3 Output libre vs estructurado · Ejemplo JSON · Mini-proyecto (3 prompts: clasificar correo, resumir reunión, redactar venta) · Cierre.
- **Cambios:** Quitar Gems, tokens/probabilidad/alucinaciones, "restricciones" de la anatomía y el "brief del proyecto de instrucción". Apertura 15'→10'. Total 2.5h→1h. Mini-proyecto = 3 prompts (ya existe, alinear).
- **Artefactos:** `slides`, `README`, `lab`, `facilitator`, `infographic`.

### Clase 2 — Make 101 + Google Cloud · 🔴 Reemplazar tema
- **v3 (10 slides):** Portada · Encuadre · Apertura · F1 ¿Qué es Make? · F2 Anatomía del escenario (trigger→módulos→acción) · F3 OAuth · F4 Google Cloud Project (Client ID + Secret, habilitar APIs) · Ejemplo real (cliente OAuth en Cloud Console) · Mini-proyecto: **registro de facturas** Drive Watch → Sheets Add Row (sin IA) · Cierre.
- **Cambios:** El tema actual (Google Sheets con IA, 3 pestañas, rangos nombrados) **se reemplaza**. Reaprovechar contenido de Make del actual S4. **OAuth + Google Cloud Project es contenido nuevo** que hay que escribir.
- **Artefactos:** todos.

### Clase 3 — API key de Gemini · 🔴 Reemplazar tema
- **v3 (10 slides):** Portada · Encuadre · Apertura · F1 ¿Qué es una API? · F2 ¿Qué es una API key? (personal, secreta, AI Studio) · Ejemplo real (pantalla AI Studio) · F3 Connection en Make vs API key directa · F4 Modelos **Gemini 2.5 Flash vs Pro** · Mini-proyecto: agregar Gemini al escenario de S2, extrae proveedor de la factura · Cierre.
- **Cambios:** Reemplaza "Google Slides con IA". Reaprovechar contenido de API del actual S5. Connection vs key directa y Flash/Pro al frente.
- **Artefactos:** todos.

### Clase 4 — JSON + Parse JSON + Variables · 🔴 Reemplazar tema
- **v3 (10 slides):** Portada · Encuadre · Apertura · F1 ¿Qué es JSON? · F2 Por qué pedir JSON a la IA (system prompt) · F3 Data Structure en Make (el "molde") · Ejemplo real (Data Structure "Venta") · F4 Parse JSON + variables · Mini-proyecto: **extracción de ventas desde Gmail** → JSON → Parse → columnas Sheet "Ventas" · Cierre.
- **Cambios:** Reemplaza "Make básico" (los conceptos base de Make se movieron a S2). Reaprovechar la parte de Parse JSON del actual S5. **Aquí vive el caso ventas/Roberto** como mini-proyecto.
- **Artefactos:** todos. Ojo: `class-04` tiene además `test/` (test diagnóstico M1) y `lab/rubric.md` — revisar alineación con el nuevo modelo de evaluación 0/100.

### Clase 5 — Plantillas con placeholders · 🔴 Reemplazar tema
- **v3 (11 slides):** Portada · Encuadre · Apertura · F1 ¿Qué es una plantilla? · F2 Placeholders `{{variable}}` · Ejemplo real (plantilla Slides) · F3 Mapeo dato→placeholder · F4 Plantillas en **Slides y Docs** (Create from Template) · F5 Formato de datos (fechas/números/monedas) · Mini-proyecto: **reporte mensual de facturas** (Search Rows → Create Presentation from Template) · Cierre.
- **Cambios:** Reemplaza "Gemini API + 2 flujos". Reaprovechar contenido de marcadores/Slides del actual S3, generalizar a Docs+Slides, sintaxis `{{variable}}`.
- **Artefactos:** todos.

### Clase 6 — Flujo end-to-end robusto · 🟠 Rehacer parcial
- **v3 (10 slides):** Portada · Encuadre · Apertura · F1 Watch vs Schedule · F2 Filtros y routers · Ejemplo real (filtro en Make) · F3 Manejo de errores y notificaciones (reintentos, alertas) · F4 Logs y depuración (History) · Mini-proyecto: **flujo completo de facturas** Drive → IA → Sheets → Docs → Email con filtros + router + error handler · Cierre.
- **Cambios:** Sobrevive "mejores prácticas / manejo de errores / logs" del actual S6. **Se cae** prompt engineering avanzado (chain of thought, few-shot, persona) y storytelling de datos. **Nuevo:** routers, filtros, error handler con reintentos.
- **Artefactos:** todos.

### Clase 7 — Proyecto integrador · 🟢 Alinear
- **v3 (8 slides):** Portada · Encuadre · Apertura · F1 Estructura del proyecto (problema→solución→arquitectura) · F2 Diagramar antes de construir · F3 Iteración construir/probar/refinar · Mini-proyecto: cada estudiante su flujo v1 con datos reales · Cierre.
- **Cambios:** Muy alineado con "Tu proyecto propio". Reencuadrar a 60 min y al esquema problema→solución→arquitectura + diagramar. Quitar "5 puntos de personalización" si no aplican.
- **Artefactos:** `slides`, `README`, `lab`, `facilitator`, `infographic`.

### Clase 8 — Exposición / Demo Day · 🟢 Alinear
- **v3 (8 slides):** Portada · Encuadre · Apertura · F1 Estructura de expo (caso→demo→resultados→aprendizajes) · F2 Preparar la demo (plan A/B/C, video de respaldo, errores en vivo) · F3 Comunicar resultados (cuanti + cuali) · Mini-proyecto: Demo Day 5 min + Q&A + feedback + roadmap personal · Cierre.
- **Cambios:** Alineado con el Demo Day actual. **v3 ya no exige** explícitamente PSDR, cálculo de ROI ni plan 30 días ni rúbrica de pares — decidir si se conservan como valor agregado o se retiran por coherencia con la fuente.
- **Artefactos:** todos. `class-08` tiene `test/` y `lab/rubric.md` — revisar.

---

## 5. Estructura objetivo de cada `slides/README.md` (patrón v3)

Todas las presentaciones nuevas siguen el mismo molde (reveal.js, separador `---`):

1. **Portada** — título + "Sesión N de 8 · 60 minutos · Online práctica en vivo"
2. **Encuadre** — Capacidad general + Objetivo de aprendizaje + lista de Fundamentos + Mini-proyecto de hoy
3. **Apertura (10 min)** — 3 preguntas al grupo + por qué importan
4. **Fundamentos (3-5)** — uno por slide: concepto + visual + a veces "Ejemplo real" como slide aparte
5. **Mini-proyecto (25-55 min)** — objetivo + pasos numerados + resultado esperado
6. **Cierre** — "Lo que te llevas" (3-4 checks) + gancho a la próxima sesión

---

## 6. Hallazgos sueltos

- **`curriculum/class-00/`** existe (solo `slides/`, 152 líneas) y **no aparece en el README**. Revisar si es intro/sesión 0 y si entra en la migración o se archiva.
- **`class-04` y `class-08`** tienen `test/` y `lab/rubric.md`. El nuevo modelo de evaluación (0/100 en clase, sin entregables post-clase) puede dejar obsoletas las rúbricas y tests — revisar explícitamente.
- El README raíz (fuente de verdad) debe actualizarse **primero**, porque todo el resto deriva de él.

---

## 7. Orden de migración recomendado

1. **README.md raíz** — nombre, duración, estructura de sesión, evaluación, caso facturas, tabla de 8 sesiones, stack (quitar Gems). Es la fuente de verdad; todo deriva de aquí.
2. **AGENTS.md / CLAUDE.md** — actualizar caso guía (Roberto→facturas), duración y nota sobre Gems.
3. **Clases en orden de severidad:** primero 🟢 7 y 8 (rápidas), luego 🟡 1 y 🟠 6, finalmente 🔴 2, 3, 4, 5 (reemplazo de tema, reaprovechando material existente que migró de sesión).
4. Por clase, seguir el pipeline de artefactos: `slides` (reflejo casi literal del PPT) → `README` → `lab` → `facilitator` → `infographic` → `test`/`rubric` si aplica.
5. Decidir destino de `class-00`, `test/` y `rubric.md`.

---

## 8. Decisiones resueltas (2026-06-03)

Principio rector: **apegarse a la fuente v3**. El contenido de tema lo dicta la fuente.

1. **ROI + plan 30 días + rúbrica de pares (S8)** → **Se eliminan.** Es decisión de *contenido de tema* (no de estructura); la v3 no los pide. La rúbrica de pares además no encaja con el modelo de evaluación 0/100 sin entregables.
2. **Gems** → **Se eliminan del todo.** La v3 no los menciona en ninguna sesión.
3. **`class-00`** → **Se actualiza a v3.** Es la orientación/resumen del curso, no un tema. Reescribir: caso (Roberto→facturas), duración (2.5h→1h), estructura de sesión, evaluación (0/100), stack (quitar Gems y "Sheets 3 pestañas"), pathway y gancho final ("Clase 01 — Prompts y Gems" → "Prompts efectivos").
4. **`test/` de M1/M2** → **Se conservan los modelos, se editan al nuevo contenido** y al modelo de evaluación 0/100.

---

## 9. Skills del pipeline y cómo se usan al editar

Los 10 skills viven en el repo hermano `../shared-skills/` (symlinks desde `.claude/skills/`). Cada artefacto de clase tiene su skill:

| Artefacto a editar | Skill | Cuándo |
|--------------------|-------|--------|
| `slides/README.md` | `class-slides` | Reflejo casi literal del PPT v3 |
| `README.md` de clase | `class-readme` | Resumen + preparación del estudiante |
| `lab/README.md` | `class-lab` | Mini-proyecto paso a paso |
| `facilitator/README.md` | `class-facilitator` | Guía pedagógica |
| `infographic/index.html` | `class-infographic` | Resumen post-clase |
| `test/` (M1/M2) | `module-test` | Test diagnóstico |
| Plan de módulo | `module-planner` | Arquitectura de 4 clases (antes de crear) |
| Auditar/refrescar módulo | `module-updater` | Detectar drift y sincronizar (este caso) |
| QA de una clase | `evaluation-class` | Antes de publicar |
| Validar Markdown | `lint-markdown` | Antes de push (enlaces, Liquid, GitHub Pages) |

> ⚠️ **Caveat en esta máquina (Windows):** los symlinks de `.claude/skills/` apuntan a una ruta Mac (`/Users/brunodiaz/...`) que no existe aquí, y los skills del curso **no aparecen en la lista de skills activos de la sesión**. Es decir, el *Skill tool* no los auto-carga. Pero el contenido real es legible en `../shared-skills/{skill}/SKILL.md`, así que se siguen sus instrucciones/plantillas **manualmente** al editar.
