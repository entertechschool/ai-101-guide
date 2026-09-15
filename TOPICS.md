# AI 101 — IA + Automatización No-Code para Profesionales — Índice de temáticas

> Índice para consultas comerciales. Generado el 2026-09-14 a partir de `README.md` y `curriculum/class-NN/README.md`. Si se mueve, renombra o añade una clase, regenerar este archivo.
> Sílabo oficial (autoridad comercial): https://raw.githubusercontent.com/entertechschool/public-sylabus/main/ai-101/index.md

**Repo:** entertechschool/ai-101-guide · **Rama publicada:** v3-2026 · **Base raw:** https://raw.githubusercontent.com/entertechschool/ai-101-guide/v3-2026/

## Resumen del curso
- **Qué construye el estudiante:** Un sistema de automatización de facturas con IA (caso guía, sesiones 1-6): subir factura a Drive → Make la detecta → Gemini extrae proveedor/monto/fecha → fila en Google Sheet → reporte mensual con plantilla en Slides/Docs enviado por Gmail, con filtros, router, manejo de errores y alertas. Luego (sesiones 7-8) un proyecto integrador propio con datos reales de su trabajo, presentado en Demo Day.
- **Formato según README:** 8 sesiones sincrónicas en vivo (el README las llama "sesiones", no "clases"), 60 min por sesión, carga total 8 horas, modalidad online. Dos bloques: "Piezas del sistema" (sesiones 1-6) y "Tu proyecto" (sesiones 7-8). Cada sesión: Apertura → Teoría/Fundamentos → Mini-proyecto en vivo → Cierre. No hay entregables post-clase.
- **Perfil de entrada según README:** Profesionales sin formación técnica que buscan automatizar tareas con IA. Sin programación.
- **Herramientas y tecnologías:** Make (escenarios, módulos, triggers, Watch, Schedule, filtros, routers, error handlers, History/logs, Connections, Blueprints Export/Import), Gemini (chat), Gemini API, Gemini Flash, Gemini Pro, Google AI Studio (API key), Google Cloud Console / Google Cloud Project (OAuth, Client ID + Secret), OAuth, Google Drive, Google Sheets, Google Docs, Google Slides, Gmail, Google Workspace, JSON, Parse JSON, Data Structure, system prompt, plantillas con placeholders `{{variable}}`, Create from Template, formatDate / formatNumber, ChatGPT y Claude (mencionados como asistentes de IA en la sesión 1). Todo con plan gratuito, sin tarjeta de crédito.
- **Proyectos:** M1 (Piezas del sistema): sistema de automatización de facturas (Drive → Make → Gemini → Sheets → Slides/Docs → Gmail) · M2 (Tu proyecto): proyecto integrador propio + Demo Day.

## Módulo 1 — Piezas del sistema (clases 01–06)
**Proyecto del módulo:** Automatización de facturas construida pieza por pieza (más casos paralelos: clasificar correos, resumir reuniones, extraer ventas desde Gmail). Registro automático Drive → Sheet, extracción de datos con Gemini, JSON estructurado, reporte mensual con plantilla y flujo end-to-end robusto.

| # | Clase | Temas clave | Herramientas | Rutas |
|---|---|---|---|---|
| 01 | Prompts efectivos | qué es un prompt, prompt profesional, anatomía Rol + Tarea + Contexto + Formato, iterar prompts, output libre vs output estructurado, JSON como formato de salida, clasificar correo de cliente, resumir reunión, redactar respuesta de venta, 3 prompts reutilizables, LLMs / modelos de lenguaje | Gemini (chat), ChatGPT, Claude, Google AI Studio (mención) | `curriculum/class-01/README.md` · `curriculum/class-01/lab/README.md` |
| 02 | Make 101 + Google Cloud | qué es Make, escenario, trigger → módulos → acción, operaciones y conexiones, OAuth (autorizar sin compartir contraseña), Google Cloud Project, Client ID + Secret, Drive Watch Files, Sheets Add a Row, primer flujo sin IA, registro automático de facturas Drive → Sheet | Make, Google Cloud Console, OAuth, Google Drive, Google Sheets | `curriculum/class-02/README.md` · `curriculum/class-02/lab/README.md` |
| 03 | API key de Gemini | qué es una API, API key (llave secreta), generar API key en Google AI Studio, seguridad de credenciales, Connection de Make vs key directa, Gemini Flash vs Gemini Pro, módulo Google AI (Gemini) en Make, IA lee documentos, extraer proveedor de la factura, columna nueva en el Sheet | Gemini API, Google AI Studio, Make (Connection), Google Drive, Google Sheets | `curriculum/class-03/README.md` · `curriculum/class-03/lab/README.md` |
| 04 | JSON + Parse JSON | qué es JSON (objetos, arrays, pares clave-valor), pedir JSON a la IA, system prompt, salida estructurada, Data Structure ("molde"), módulo Parse JSON, variables, mapear campos a columnas, Gmail Watch Emails, extracción de ventas desde correos informales, vendedor/cliente/producto/monto/fecha, texto libre → datos estructurados | Make (Parse JSON, Data Structure), Gemini API, Gmail, Google Sheets | `curriculum/class-04/README.md` · `curriculum/class-04/lab/README.md` |
| 05 | Plantillas con placeholders | qué es una plantilla (formato fijo, datos variables), placeholders `{{variable}}`, mapeo de datos a placeholders, Create from Template en Slides/Docs, Sheets Search Rows, agregados (total, top proveedor, número de facturas), formato de fechas/números/monedas, formatDate / formatNumber, reporte mensual de facturas, generación automática de documentos y presentaciones, guardar en Drive / enviar por correo | Make (Create from Template, formatDate, formatNumber), Google Slides, Google Docs, Google Sheets, Google Drive, Gmail | `curriculum/class-05/README.md` · `curriculum/class-05/lab/README.md` |
| 06 | Flujo end-to-end robusto | trigger Watch (por evento) vs Schedule (programado), filtros, routers, lógica condicional, rutas por monto (alerta al jefe), manejo de errores, error handler, reintentos, notificaciones y alertas por email, logs y depuración con History de Make, casos límite (no-PDF, factura sin total), integración de todas las piezas, flujo completo Drive → IA → Sheets → Docs → Gmail, sistema de producción | Make (filtros, router, error handler, History), Gemini API, Google Drive, Google Sheets, Google Docs/Slides, Gmail | `curriculum/class-06/README.md` · `curriculum/class-06/lab/README.md` |

## Módulo 2 — Tu proyecto (clases 07–08)
**Proyecto del módulo:** Proyecto integrador propio: flujo automatizado v1 funcionando con datos reales del trabajo del estudiante (contabilidad, atención al cliente, marketing, ventas, RR.HH., etc.), sustentado en Demo Day con demo en vivo de 5 minutos y roadmap personal.

| # | Clase | Temas clave | Herramientas | Rutas |
|---|---|---|---|---|
| 07 | Proyecto integrador | transferir el método a un caso real propio, problema → solución → arquitectura, diagramar el flujo (trigger → módulos → output) antes de construir, adaptar Sheet/prompts/plantillas a tu industria, v1 mínima, iterar con datos reales, duplicar escenarios (Export/Import Blueprint), debug de escenarios, acompañamiento 1 a 1, casos: contabilidad, atención al cliente (tickets), marketing (reportes de campaña), ventas (seguimiento de leads), RR.HH. (onboarding) | Make (Blueprints, debug), Gemini API, Google Sheets, Google Docs/Slides, Google Drive, Gmail | `curriculum/class-07/README.md` · `curriculum/class-07/lab/README.md` |
| 08 | Exposición / Demo Day | estructura de exposición caso → demo → resultados → aprendizajes, demo en vivo de 5 minutos, plan B de demo (video de respaldo), comunicar resultados cuantitativos (tiempo ahorrado, costo, items procesados) y cualitativos, Q&A, feedback entre pares, roadmap personal de próximas automatizaciones, presentación de proyecto técnico | Sistema propio en Make + Gemini + Google Workspace | `curriculum/class-08/README.md` · `curriculum/class-08/lab/README.md` |

## Búsqueda rápida por tema

| Tema / palabra clave | Clase(s) |
|---|---|
| Alertas, notificaciones cuando algo falla | 06 |
| Alucinaciones, cómo funciona un modelo de lenguaje, LLM | 01 |
| API, qué es una API | 03 |
| API key, llave de API, credenciales de IA | 03 |
| Arquitectura del flujo, diagramar antes de construir | 07 |
| Asistentes de IA, IA generativa, ChatGPT, Claude, Gemini | 01 |
| Atención al cliente, tickets (caso propio) | 07 |
| Automatización, automatizar tareas, flujos automáticos | 02, 03, 04, 05, 06, 07 |
| Blueprints de Make, exportar/importar escenarios, duplicar | 07 |
| Casos límite, pruebas con archivos difíciles | 06 |
| Clasificar correos con IA | 01, 04 |
| Client ID, Client Secret, credenciales OAuth | 02 |
| Comunicar resultados, métricas de impacto (tiempo, costo, items) | 08 |
| Conexiones, Connection en Make | 02, 03 |
| Contabilidad, facturas (caso guía) | 02, 03, 04, 05, 06 |
| Create from Template, generar Doc/Slide desde plantilla | 05 |
| Data Structure, molde del JSON | 04 |
| Debug, depurar, History de Make, logs | 06, 07 |
| Demo Day, exposición, sustentación, presentación final | 08 |
| Demo en vivo, plan B, video de respaldo | 08 |
| Documentos automáticos, reportes automáticos, Google Docs | 05, 06 |
| Drive, Google Drive, carpeta de entrada, trigger por archivo | 02, 03, 05, 06 |
| Email, correo, Gmail, enviar reportes por correo | 04, 05, 06 |
| Error handler, manejo de errores, reintentos | 06 |
| Escenario de Make, módulos, operaciones | 02 |
| Extracción de datos de documentos con IA, leer facturas | 03, 04 |
| Extraer ventas desde Gmail, correos informales → tabla | 04 |
| Feedback entre pares, Q&A | 08 |
| Filtros, condiciones, qué procesar | 06 |
| Flujo end-to-end, sistema completo, producción | 06 |
| Formato de fechas, números y monedas, formatDate, formatNumber | 05 |
| Gemini (chat), diseñar y probar prompts | 01 |
| Gemini API, Gemini en Make, módulo Google AI | 03, 04, 05, 06, 07 |
| Gemini Flash vs Gemini Pro, elegir modelo | 03 |
| Gmail Watch Emails, trigger por correo | 04 |
| Google AI Studio | 01, 03 |
| Google Cloud, Google Cloud Console, Google Cloud Project | 02 |
| Google Sheets, hoja de cálculo, Add a Row, Search Rows | 02, 03, 04, 05, 06 |
| Google Slides, presentaciones automáticas | 05, 06 |
| Google Workspace | 02, 03, 04, 05, 06, 07 |
| IA en flujos, integrar IA en automatizaciones | 03, 04, 06, 07 |
| Iterar prompts, refinar resultados | 01, 07 |
| JSON, objetos, arrays, clave-valor | 01, 04 |
| Lógica condicional, rutas, bifurcación | 06 |
| Make, make.com, plataforma no-code | 02, 03, 04, 05, 06, 07 |
| Mapeo de datos, mapear campos a columnas / placeholders | 04, 05 |
| Marketing, reportes de campaña (caso propio) | 07 |
| Mini-proyectos en vivo, práctica en clase | 01, 02, 03, 04, 05, 06, 07, 08 |
| No-code, sin código, sin programar | 02, 03, 04, 05, 06, 07 |
| OAuth, autorizar apps sin compartir contraseña | 02 |
| Output libre vs output estructurado | 01, 04 |
| Parse JSON, convertir texto en variables | 04, 06 |
| Placeholders `{{variable}}` | 05 |
| Plantillas, templates, reportes con formato fijo | 05, 06 |
| Presentar un proyecto técnico, exposición de 5 minutos | 08 |
| Prompt, prompting, prompts efectivos, prompts profesionales | 01 |
| Prompt: Rol + Tarea + Contexto + Formato | 01 |
| Proyecto integrador, proyecto propio, caso real | 07, 08 |
| Proyecto final, entregable final | 07, 08 |
| Redactar respuestas de venta con IA | 01 |
| Registro automático de facturas Drive → Sheet | 02 |
| Reporte mensual, reporte automático | 05, 06 |
| Resumir reuniones con IA | 01 |
| Roadmap personal, próximas automatizaciones | 08 |
| Router, rutas múltiples | 06 |
| RR.HH., onboarding (caso propio) | 07 |
| Salida estructurada de la IA, structured output | 01, 04 |
| Schedule, trigger programado, por lotes, a hora fija | 05, 06 |
| Seguridad de credenciales, no exponer API keys | 03 |
| System prompt | 04 |
| Transferir el método a otro caso, adaptar a tu industria | 07 |
| Trigger, evento que dispara el flujo | 02, 06, 07 |
| v1 mínima, primera versión funcional, iterar | 07 |
| Variables en Make, arrastrar campos a módulos | 04 |
| Ventas, seguimiento de leads (caso propio) | 04, 07 |
| Watch, trigger por evento, Watch Files | 02, 06 |
| Watch vs Schedule | 06 |

## Lo que NO cubre (según el material)
- **Sin programación / sin escribir código:** el README define la audiencia como "Profesionales sin formación técnica... **Sin programación.**" y el curso se construye "todo sin escribir código".
- **Sin tarjeta de crédito ni herramientas de pago:** "Todas las herramientas funcionan con plan gratuito. No se requiere tarjeta de crédito."
- **Sin entregables post-clase / sin tareas:** "No hay entregables post-clase."
- **Sesión 2 sin IA:** el registro Drive → Sheet se construye "sin IA aún"; la IA entra en la sesión 3.

## Excepciones de rutas
Ninguna. Las 8 clases siguen `curriculum/class-NN/README.md` + `curriculum/class-NN/lab/README.md`. (Nota: `curriculum/class-01/MASTER.md` existe pero está deprecado y no se indexa; `class-00` es orientación y se excluye.)

## Discrepancias con el sílabo oficial
Revisadas el 2026-09-15 contra el material (`curriculum/class-00/README.md`, `curriculum/class-01/README.md`, `curriculum/class-01/lab/README.md`, `README.md`). Todas resueltas salvo la nº 6, que no era una discrepancia real.

1. **Duración / horas — RESUELTO (CAMBIO SENSIBLE).** El sílabo publicaba 20 h ("Clases en vivo: 20 · Total: 20"); el README y `class-00/README.md` confirman 8 sesiones × 60 min = 8 h. Se corrigió la tabla "Inversión de tiempo" del sílabo a 8 h. "4 semanas" y "2 sesiones por semana" no se tocaron: siguen siendo coherentes (4 × 2 = 8 sesiones).
2. **Nombre del curso — RESUELTO.** H1 del sílabo alineado a "AI 101 — IA + Automatización No-Code para Profesionales" (igual al README). El `title:` del front matter no se tocó.
3. **Módulos — RESUELTO.** El sílabo se reagrupó a "Módulo 1: Piezas del Sistema" (sesiones 1-6) y "Módulo 2: Tu Proyecto" (sesiones 7-8), igual que el README.
4. **Anatomía del prompt (sesión 1) — RESUELTO.** Se quitó "+ Restricciones" del sílabo (Resultados de aprendizaje y Sesión 1); queda "Rol + Tarea + Contexto + Formato" como en `class-01/README.md`.
5. **Alucinaciones en sesión 1 — RESUELTO.** Se quitó la mención a "por qué alucina" del sílabo (Resultados de aprendizaje y Sesión 1), porque `class-01/README.md` y su lab no lo enseñan (solo hay una lectura sugerida y opcional sobre LLMs).
6. **Perfil de entrada — no es una discrepancia real, sin cambios.** El sílabo detalla "manejo básico de navegación web, correo y Google Drive" como prerequisito; el README no lo detalla pero tampoco lo contradice, y es coherente con el uso de Drive/Gmail en las clases 02 y 04. Se dejó igual.

Proyectos y herramientas coinciden en ambas fuentes (Make + Gemini + Google Workspace, caso facturas, proyecto integrador + Demo Day).
