## Feedback del equipo:

1. Bajarle % al desarrollo de negocios.
2. Realmente cuánto necesitamos en tiempo para cada módulo.
3. Apuntar bien a qué personas se puede encontrar.

---

# PROPUESTA DE AJUSTES: AI Product Developer (No-Developers)

## ANÁLISIS DEL FEEDBACK

### 1. "Bajarle % al desarrollo de negocios"

**Diagnóstico actual:**
- Módulo 3 tiene mucho énfasis en GTM, stakeholders, pitch decks
- Módulo 4 dedica clase completa a monetización y financial modeling
- ~25-30% del curso está en territorio "business development"

**Problema:** El curso promete formar "AI Product Developers", no "AI Business Strategists". Hay desbalance hacia skills de BD vs. construcción de producto.

---

### 2. "Realmente cuánto necesitamos en tiempo para cada módulo"

**Diagnóstico actual:**
- 4 módulos × 8 horas = 32 horas totales
- Cada clase = 2 horas (asume ritmo perfecto sin fricciones)
- No hay tiempo de absorción entre módulos

**Problema:** 2 horas/clase es optimista para audiencia no-técnica que está aprendiendo herramientas nuevas. Puede generar:
- Overwhelm por velocidad
- Entregables incompletos o superficiales
- Frustración con herramientas no-code (curva de aprendizaje)

---

### 3. "Apuntar bien a qué personas apuntamos"

**Diagnóstico actual:**
- Descripción vaga: "profesionales digitales sin background técnico"
- No especifica niveles de seniority, roles concretos, o contexto laboral

**Problema:** Sin target claro, el curso intenta servir a todos y termina siendo genérico.

---

## PROPUESTA DE AJUSTES MÓDULO A MÓDULO

### MÓDULO 1: FUNDAMENTOS + HERRAMIENTAS
**Estado actual:** 4 clases × 2h = 8 horas

#### Ajustes propuestos:

**Clase 1: Fundamentos de IA y Oportunidades en Product Management**
- **MANTENER** como está (necesaria para nivelar conocimiento)
- Agregar: 15 min de "expectativas realistas" sobre lo que SÍ/NO podrán hacer al final del curso

**Clase 2: Design Thinking + IA: Identificar Problemas Reales**
- **REDUCIR** componente de Design Thinking completo (muy denso)
- **ENFOCAR** solo en: problem discovery + Jobs-to-be-Done
- Eliminar: Ejercicio de role-play (consume mucho tiempo, bajo ROI)

**Clase 3: Validación Rápida de Ideas con Usuarios**
- **MANTENER** estructura, pero simplificar experimentos
- **ELIMINAR** referencia a "smoke tests" y "concierge MVP" (demasiados conceptos)
- **ENFOCAR** solo en: landing page + entrevistas de validación

**Clase 4: Herramientas No-Code IA: Tu Stack Productivo**
- **CRÍTICO:** Esta clase está sobrecargada
- **DIVIDIR** en dos opciones:
  - **Opción A:** Extender a 3 horas (clase especial)
  - **Opción B:** Dividir en Clase 4A (Claude + v0.dev) y 4B (Make + Airtable)
- **RECOMENDACIÓN:** Opción B para que dominen herramientas antes de usarlas

**Resultado Módulo 1:**
- **Nuevo tiempo:** 5 clases × 2h = 10 horas
- **Entregables ajustados:**
  - Problema validado (simplificado, no requiere 10 entrevistas)
  - Stack configurado (con troubleshooting time real)
  - PRD v0.1 (template guiado, no desde cero)

---

### MÓDULO 2: DESCUBRIMIENTO + PROTOTIPADO
**Estado actual:** 4 clases × 2h = 8 horas

#### Ajustes propuestos:

**Clase 5: Análisis de Mercado y Competencia Asistido por IA**
- **REDUCIR MUCHO** - Esta clase está sobrecargada
- **ELIMINAR:** Porter's 5 Forces, SWOT completo (demasiado estratégico/BD)
- **ENFOCAR:** 
  - Análisis competitivo directo (5-7 competidores máximo)
  - Feature comparison matrix
  - Identificar 1-2 diferenciadores clave
- **Duración ajustada:** De 2h → 1.5h (liberar 30 min para otra actividad)

**Clase 6: Definición de MVP: Funcionalidades Críticas**
- **MANTENER** esencia pero simplificar
- **ELIMINAR:** RICE framework completo (muy complejo para primera iteración)
- **ENFOCAR:** 
  - Must-have vs. Nice-to-have (simple)
  - User stories básicas (3-5 máximo)
  - PRD con template super guiado
- **EXTENDER:** De 2h → 2.5h (la definición de MVP es CRÍTICA)

**Clase 7: Prototipado Rápido con Herramientas No-Code**
- **MANTENER** estructura
- **AJUSTAR:** Expectativa de "3-5 pantallas" → "2-3 flujos clave"
- **AGREGAR:** 20 min de troubleshooting común con v0.dev

**Clase 8: Construcción del Proyecto: MVP Funcional**
- **CRÍTICO:** 2 horas NO alcanzan para integrar todo
- **EXTENDER:** A 3 horas MÍNIMO
- **ALTERNATIVA:** Dividir en:
  - Clase 8A: Integración frontend + IA (Claude API / v0.dev)
  - Clase 8B: Integración backend (Make + Airtable)
- **RECOMENDACIÓN:** Clase de 3 horas + office hours asincrónico

**Resultado Módulo 2:**
- **Nuevo tiempo:** 4-5 clases, 9.5-10 horas
- **Entregables ajustados:**
  - Competitive analysis (1 página, no report extenso)
  - PRD funcional (template 80% pre-llenado)
  - Prototipo funcional al 70% (no 100% - realista)

---

### MÓDULO 3: VALIDACIÓN + LANZAMIENTO
**Estado actual:** 4 clases × 2h = 8 horas

#### Ajustes propuestos (AQUÍ ESTÁ EL MAYOR CAMBIO):

**Clase 9: Testing y Validación de MVP en Usuarios Reales**
- **MANTENER** - Esta es core de producto
- **AJUSTAR:** Expectativa de "10+ usuarios" → "5-7 usuarios beta"
- **ENFOCAR:** Calidad de insights sobre cantidad

**Clase 10: Métricas, KPIs y Dashboards para Productos IA**
- **MANTENER** esencia pero simplificar
- **ELIMINAR:** AARRR completo, North Star Metric (demasiado avanzado)
- **ENFOCAR:** 
  - 3-5 métricas clave máximo
  - Dashboard simple (Google Sheets, no Looker Studio)

**Clase 11: Go-to-Market Strategy → CAMBIAR A "Iteración y Mejora del MVP"**
- **ELIMINAR COMPLETAMENTE:** GTM strategy, growth loops, pitch deck
- **NUEVO ENFOQUE:**
  - Priorización de mejoras post-testing
  - Iteración rápida con feedback de usuarios
  - Preparar v1.1 del producto
  - Documentación de decisiones de producto
- **JUSTIFICACIÓN:** Un PM debe iterar producto antes de lanzarlo. GTM es rol de Marketing/Growth.

**Clase 12: Gestión de Stakeholders → CAMBIAR A "Preparación de Portfolio y Presentación"**
- **ELIMINAR:** Stakeholder mapping, storytelling ejecutivo (muy BD)
- **NUEVO ENFOQUE:**
  - Documentar proceso completo (case study)
  - Crear demo efectiva del MVP (video Loom)
  - Preparar presentación técnica (no pitch)
  - Feedback de pares
- **JUSTIFICACIÓN:** Un PM debe saber documentar y comunicar su trabajo, pero no necesita hacer "executive presentations" en este nivel.

**Resultado Módulo 3:**
- **Nuevo tiempo:** 4 clases × 2h = 8 horas (sin cambio)
- **Nuevo enfoque:** 
  - ❌ Menos: GTM, stakeholders, pitch decks, estrategia de BD
  - ✅ Más: Iteración de producto, mejora basada en datos, documentación

---

### MÓDULO 4: ESCALABILIDAD + CIERRE
**Estado actual:** 4 clases × 2h = 8 horas

#### Ajustes propuestos:

**Clase 13: Escalado: De MVP a Producto Maduro**
- **MANTENER** concepto pero aterrizar
- **AJUSTAR:** Roadmap de 6 meses → Roadmap de 3 meses (más realista)
- **AGREGAR:** Cuándo y cómo involucrar a developers (transición a código)

**Clase 14: Ética, Sesgo y Responsabilidad en Productos IA**
- **MANTENER** - Es diferenciador importante del curso
- **SIMPLIFICAR:** IEEE, EU AI Act (demasiado denso)
- **ENFOCAR:** 
  - 3-4 principios éticos aplicados
  - Checklist práctico de evaluación
  - Casos reales de productos con issues éticos

**Clase 15: Monetización y Modelos de Negocio → CAMBIAR A "Viabilidad Técnica y Próximos Pasos"**
- **REDUCIR DRÁSTICAMENTE** financial modeling
- **NUEVO ENFOQUE:**
  - Evaluar viabilidad técnica del MVP
  - Identificar limitaciones del stack no-code
  - Cuándo escalar vs. cuando pivotar
  - Roadmap personal: próximos skills a desarrollar
- **MANTENER (simplificado):** 
  - Modelos de pricing básicos (15 min)
  - Unit economics high-level (15 min)
- **JUSTIFICACIÓN:** Financial modeling extenso es trabajo de Finance/BD, no de PM

**Clase 16: Presentación Final de Proyecto**
- **MANTENER** estructura
- **AJUSTAR:** 
  - Presentaciones de 10 min (no 15)
  - Enfoque en producto y decisiones técnicas
  - Eliminar "evaluación de expertos externos" (genera ansiedad innecesaria)
  - Agregar: gallery walk informal de portfolios

**Resultado Módulo 4:**
- **Nuevo tiempo:** 4 clases × 2h = 8 horas (sin cambio)
- **Nuevo enfoque:**
  - ❌ Menos: Monetización extensa, financial modeling, BD strategy
  - ✅ Más: Viabilidad técnica, transición a desarrollo real, growth personal

---

## RESUMEN COMPARATIVO: ANTES vs. DESPUÉS

| Aspecto | ANTES | DESPUÉS |
|---------|-------|---------|
| **Total de clases** | 16 clases | 17-18 clases |
| **Total de horas** | 32 horas | 36-38 horas |
| **% Business Development** | ~30% | ~10% |
| **% Construcción de Producto** | ~50% | ~70% |
| **% Herramientas No-Code** | ~20% | ~20% |
| **Clases eliminadas (BD)** | 0 | GTM Strategy, Stakeholder Mgmt, Monetización (parcial) |
| **Clases agregadas (Producto)** | 0 | Iteración del MVP, Viabilidad Técnica, Herramientas (split) |

---

## PROPUESTA DE DURACIÓN REALISTA POR MÓDULO

### Opción A: Extensión Moderada (Recomendada)
- **Módulo 1:** 10 horas (5 clases × 2h)
- **Módulo 2:** 10 horas (4 clases × 2h + 1 clase × 3h)
- **Módulo 3:** 8 horas (4 clases × 2h)
- **Módulo 4:** 8 horas (4 clases × 2h)
- **TOTAL:** 36 horas / 9 semanas

### Opción B: Extensión Realista (Más cómoda)
- **Módulo 1:** 12 horas (6 clases × 2h)
- **Módulo 2:** 11 horas (5 clases × 2h + office hours)
- **Módulo 3:** 8 horas (4 clases × 2h)
- **Módulo 4:** 8 horas (4 clases × 2h)
- **TOTAL:** 39 horas / 10 semanas

### Opción C: Ultra-Realista (Sin prisa)
- **Módulo 1:** 12 horas (6 clases × 2h)
- **Módulo 2:** 12 horas (6 clases × 2h)
- **Módulo 3:** 10 horas (5 clases × 2h)
- **Módulo 4:** 10 horas (5 clases × 2h)
- **TOTAL:** 44 horas / 11 semanas

**Recomendación:** **Opción A (36h/9 semanas)** - Balance entre ambición y realismo

---

## PÚBLICO OBJETIVO ATERRIZADO Y REALISTA

### PERFIL PRINCIPAL (70% del cohort)

**Título del rol:**
- Product Managers junior/mid-level (1-4 años de experiencia)
- Associate Product Managers
- Product Owners
- Technical Program Managers (sin background de código)

**Contexto laboral:**
- Trabajan en startups o empresas tech-adjacent
- Ya gestionan productos digitales (web/mobile)
- No tienen equipo técnico propio O tienen acceso limitado a developers
- Sienten que "la IA los está dejando atrás"

**Skills actuales:**
- ✅ Saben usar Google Workspace, Notion, herramientas de PM básicas
- ✅ Entienden conceptos de UX, agile, roadmaps
- ✅ Han hecho research de usuarios o A/B testing
- ❌ NO saben programar (máximo HTML/CSS básico)
- ❌ NO han construido productos desde cero
- ❌ NO tienen experiencia con APIs o integraciones técnicas

**Motivaciones:**
- Quieren agregar "IA" a su producto actual pero no saben por dónde empezar
- Sienten que necesitan "hablar el idioma" de IA para no quedar obsoletos
- Quieren ser más autosuficientes y no depender 100% de developers
- Buscan diferenciarse en el mercado laboral
- Consideran emprendimiento en el futuro (side project o startup)

**Frustraciones:**
- "Todos los cursos de IA asumen que sé programar"
- "No sé si mi idea es viable técnicamente"
- "Mi equipo de dev siempre me dice que mis ideas son muy difíciles"
- "Veo productos IA increíbles pero no sé cómo empezar a construir"

**Industrias representadas:**
- Fintech, Edtech, Healthtech, E-commerce, SaaS B2B, Marketplaces

---

### PERFIL SECUNDARIO (20% del cohort)

**Título del rol:**
- Founders técnicos de startups early-stage (sin equipo de producto)
- Technical Co-founders que necesitan skills de PM
- Engineering Managers que quieren entender producto
- Designers con mentalidad de producto

**Contexto laboral:**
- Están construyendo o validando una startup
- Tienen skills técnicos pero no de producto/negocio
- Necesitan moverse rápido con recursos limitados

**Motivaciones:**
- Construir MVP rápido sin contratar equipo completo
- Validar ideas antes de buscar funding
- Aprender metodologías de producto para liderar mejor

---

### PERFIL TERCIARIO (10% del cohort)

**Título del rol:**
- Profesionales de áreas adyacentes queriendo pivotar:
  - Customer Success Managers
  - Marketing Managers (product marketing)
  - Operations Managers
  - Business Analysts

**Contexto laboral:**
- Trabajan cerca de producto pero no lo gestionan directamente
- Quieren hacer transición de carrera a PM
- Ven IA como oportunidad de reposicionarse

**Motivaciones:**
- Cambio de carrera hacia producto
- Upskilling para promoción interna
- Prepararse para mercado laboral competitivo

---

### ANTI-PERFIL (NO son nuestro público)

❌ **Developers queriendo agregar PM skills** 
- Razón: Ya saben construir, necesitan curso diferente

❌ **Ejecutivos C-level buscando "entender IA"**
- Razón: Necesitan curso estratégico, no hands-on

❌ **Personas sin experiencia laboral en tech**
- Razón: Curva de aprendizaje demasiado pronunciada

❌ **Consultores/Agencias buscando revender servicios**
- Razón: Motivación transaccional, no de aprendizaje profundo

---

### CRITERIOS DE ADMISIÓN SUGERIDOS

Para asegurar cohort homogéneo y resultados consistentes:

**Requisitos mínimos:**
1. Experiencia laboral en empresa tech o digital (1+ año)
2. Familiaridad con metodologías ágiles o PM básico
3. Acceso a computadora (Mac/Windows, no tablets)
4. Inglés de lectura (herramientas están en inglés)
5. Disponibilidad de 6-8 horas/semana (clases + homework)

**Proceso de admisión:**
1. Formulario de aplicación con preguntas filtro
2. Video de presentación (2 min): contexto + motivación + proyecto ideal
3. Mini-assignment: "Identifica un problema en tu industria que IA podría resolver" (1 página)

**Señales de buen fit:**
- Menciona producto específico que quiere mejorar/construir
- Demuestra curiosidad genuina por IA (no solo hype)
- Tiene claridad sobre qué NO sabe y quiere aprender
- Muestra disposición a aprender herramientas nuevas
- Comprende que será trabajo intenso (no curso pasivo)

---

## RECOMENDACIONES FINALES

### 1. Sobre Business Development
**Mantener:** 
- Análisis competitivo básico (necesario para contexto)
- Pricing models high-level (15-20 min, no más)
- Storytelling de producto (para presentar trabajo)

**Eliminar/Reducir:**
- GTM strategy completa
- Financial modeling extenso
- Stakeholder management corporativo
- Growth loops y estrategias de distribución

### 2. Sobre Duración
**Implementar Opción A:**
- 36 horas / 9 semanas
- 2 clases/semana (martes y jueves)
- 1 semana de buffer entre Módulo 2 y 3 (para catch-up)

### 3. Sobre Público Objetivo
**Enfocar marketing en:**
- PMs junior/mid queriendo especializarse en IA
- Founders técnicos necesitando skills de producto
- Profesionales tech-adjacent buscando pivotar

**Comunicación clara:**
- "No necesitas saber programar"
- "Construirás un MVP funcional desde cero"
- "Aprenderás herramientas que puedes usar el lunes siguiente"

