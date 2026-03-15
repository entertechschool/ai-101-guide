# CLAUDE.md - AI 101 Guide

## Instrucciones Base

Ver **[AGENTS.md](AGENTS.md)** para convenciones del repositorio, estructura, tono, límites y pipeline de generación. Este archivo contiene solo configuración específica de Claude Code.

---

## Skills Disponibles

| Skill | Propósito | Output |
|-------|-----------|--------|
| `module-planner` | Planificar módulo completo (4 clases) | `MODULE-PLAN.md` |
| `class-readme` | README de clase para estudiante | `README.md` |
| `class-lab` | Laboratorio paso a paso | `lab/README.md` |
| `class-slides` | Presentación reveal.js | `slides/README.md` |
| `class-facilitator` | Guía pedagógica | `facilitator/README.md` |
| `evaluation-class` | Verificar calidad | Reporte |
| `lint-markdown` | Validar Markdown para GitHub Pages | Reporte/Corrección |
| `module-test` | Test diagnóstico por módulo | `test/README.md` + `test/questions.md` |
| `class-infographic` | Infografía post-clase | `infographic/index.html` + `infographic/image-prompts.md` |
| `module-updater` | Auditar y actualizar módulo existente | Reporte + ediciones |

Ver detalles en `.claude/skills/*/SKILL.md`

---

## Skills Compartidos

Los 10 skills vienen de [shared-skills](https://github.com/entertechschool/shared-skills) via symlinks:

```
.claude/skills/{skill} → ../shared-skills/{skill}
```

- **Sync:** `../shared-skills/bin/ets-sync-skills` (auto-detecta ruta, zero config)
- **Actualizar skills:** editar en `shared-skills/` y correr sync
- **Override local:** reemplazar symlink con directorio real (el repo local tiene prioridad)

---

## Progreso del Curso

| Módulo | Estado | Proyecto |
|--------|--------|----------|
| M1 (1-4) | Completo | Portfolio Profesional IA (Fundamentos) |
| M2 (5-8) | Completo | Portfolio Profesional IA (Aplicaciones) |

---

## Commits

Formato: `tipo: descripción concisa`
Types: `feat:` `fix:` `docs:` `refactor:` `style:`
