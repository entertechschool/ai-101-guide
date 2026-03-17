> 📦 **Módulo 2:** Clase 3 de 4

# Clase 07: Mi Agente Real

## Resumen

En las Clases 05 y 06 construiste un agente que **clasifica** mensajes: la IA leía un input, asignaba una categoría (URGENTE/CONSULTA/VENTA) y un Router enviaba emails etiquetados. Hoy das el siguiente paso: **un agente que genera contenido profesional.**

La diferencia clave: en vez de 1 IA que clasifica, encadenas **2 IAs**. La primera ANALIZA tu input desordenado y extrae estructura (JSON). La segunda GENERA un email HTML profesional a partir de esa estructura. Escribes garabatos → recibes un email profesional en tu correo. Al final, tienes un agente deployado en Vercel que cualquiera puede usar.

---

## ¿Por qué te sirve?

| C05-C06: Clasificar | C07: Generar |
|---------------------|-------------|
| 1 IA que pone etiquetas | 2 IAs encadenadas que crean contenido |
| Output: categoría (URGENTE) | Output: email profesional completo |
| Router decide la ruta | Pipeline transforma los datos |
| Caso de tutorial (PetShop) | TU caso real (3 escenarios o propio) |
| Entrega en Google Doc | Deploy público en Vercel (portfolio real) |

> "De clasificar a generar. De tutorial a proyecto publicado."

---

## Insight: "2 cerebros son mejor que 1"

```
Arquitectura C07:

Form v0 (textarea + campo extra + email)
    │
    ▼
Webhook (Make)
    │
    ▼
OpenRouter #1 — ANALIZAR
(input crudo → JSON estructurado)
    │
    ├──────────────────┐
    ▼                  ▼
Google Sheets      OpenRouter #2 — GENERAR
(registra log)     (JSON → email HTML profesional)
                       │
                       ▼
                   Gmail → email al usuario
```

**¿Por qué 2 IAs?** Especialización. OR#1 solo analiza (extrae estructura del caos). OR#2 solo genera (produce contenido profesional). Cada una hace un trabajo = mejor calidad que pedirle todo a una sola.

---

## ¿Qué haremos en clase?

1. **Diseñar tu caso** — Elegir escenario (o proponer el tuyo) + personalizar SystemPrompts con Claude
2. **Construir tu agente** — Form v0 + Make con 5 módulos (Webhook → OR#1 → Sheets → OR#2 → Gmail)
3. **Verificar** — Deploy en Vercel + 2 mensajes de prueba end-to-end

---

## Los 3 escenarios

| # | Escenario | Escribes... | Recibes... |
|---|-----------|-------------|------------|
| 1 | Clarificador de Ideas | Idea desordenada | Brief profesional con fortalezas, gaps y próximos pasos |
| 2 | Procesador de Notas de Reunión | Garabatos y abreviaturas | Acta ejecutiva con tabla de tareas y decisiones |
| 3 | Generador de Feedback Profesional | Feedback crudo/emocional | Guía SBI con reformulaciones y tips de entrega |
| 4 | Tu propio caso | Tu input real | Tu output profesional (diseñado con plantilla guiada) |

---

## Objetivos de aprendizaje

1. Diseñar un caso de agente generativo con 2 SystemPrompts encadenados (analizar + generar)
2. Construir un pipeline de 5 módulos en Make con 2 llamadas a OpenRouter
3. Deployar tu agente en Vercel como URL pública funcional

---

## Preparación para la clase

### Obligatorio

1. **Elegir tu escenario** — Revisa la tabla de 3 escenarios y decide cuál te interesa (o prepara tu caso propio)
2. **API key de OpenRouter** funcionando (la misma de C05-C06)
3. **Claude abierto** — lo usarás como socio pensante para personalizar SystemPrompts (callback C03)

### Reflexiona antes de clase

- ¿Qué información desordenada recibes regularmente que te gustaría que se transformara automáticamente en algo profesional?
- ¿Notas de reunión? ¿Ideas sueltas? ¿Feedback que no sabes cómo dar?

---

## Glosario de nuevos términos

- **Encadenamiento de IAs**: Usar el output de una IA como input de otra — la primera analiza, la segunda genera
- **Pipeline**: Secuencia de pasos donde cada módulo transforma los datos para el siguiente
- **Deploy**: Publicar tu proyecto en internet para que cualquiera pueda acceder

---

## Recursos Adicionales

- [OpenRouter Models](https://openrouter.ai/models){:target="_blank"} - Modelos disponibles y precios
- [Vercel Deployments](https://vercel.com/docs/deployments){:target="_blank"} - Documentación de deploy

---

## Herramientas necesarias

- [ ] 💻 Laptop con Make abierto (crear nuevo escenario)
- [ ] 🧠 Claude abierto (socio pensante para SystemPrompts)
- [ ] 🔑 API key de OpenRouter (la misma de C05-C06)
- [ ] 📧 Gmail configurado en Make (para recibir los emails generados)

---

## Preview C08: Demo Day + GitHub + LinkedIn

> **Tarea para la próxima clase:**
> 1. Crear cuenta en **GitHub** si no tienes (github.com — es gratis)
> 2. Tener tus **2 SystemPrompts** (OR#1 + OR#2) copiados y accesibles
> 3. Verificar que tu **URL de Vercel** funciona públicamente
> 4. Tener cuenta de **LinkedIn** abierta
> 5. Tener cuenta de **Gemini** (gemini.google.com)
> 6. Pulir SystemPrompts — probar con 3+ mensajes variados
