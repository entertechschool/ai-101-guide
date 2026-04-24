> **Módulo 1:** Clase 4 de 4 — Lab Calificado

# Clase 04: Make básico (sin IA)

## Resumen

Hoy ves por primera vez el sistema funcionando end-to-end. Vas a construir dos escenarios en Make que conectan las piezas que armaste en las clases anteriores: el Sheet (Clase 2) y la plantilla de Slides (Clase 3). Todavía sin IA — solo Gmail, Sheets, Slides y exportación a PDF.

El primer escenario captura correos entrantes y registra filas automáticamente en tu pestaña operativa usando un **Instant Trigger** (reacción en 2-5 segundos). El segundo escenario toma los datos del Sheet, duplica la plantilla de Slides, reemplaza los marcadores crudos y calculados, exporta PDF y lo envía por correo. Este es el **lab calificado** del Módulo 1 — tu evaluación integradora.

---

## ¿Por qué te sirve?

- **Make ejecuta ~10 operaciones por cada reporte completo.** En el plan gratuito (1,000 ops/mes) caben 100+ reportes sin pagar nada. Para la mayoría de profesionales, es gratis de verdad.
- **Un Instant Trigger de Gmail reacciona en segundos, no minutos.** La diferencia con Scheduled (cada 15 min) es el "efecto WOW" cuando tu audiencia ve el sistema actualizarse en vivo.
- **Aprender Make abre la puerta a 1,500+ integraciones.** Slack, Notion, HubSpot, WhatsApp Business — todo conectable. Lo que construyes hoy es solo la primera automatización de muchas.

---

## 🎯 ¿Qué haremos en clase?

1. **Exploraremos los conceptos de Make** - Descubrirás escenarios, módulos, operaciones, conexiones y la diferencia Instant vs Scheduled.
2. **Construirás el escenario Gmail → Sheet** - Configurarás un Instant Trigger con filtro y agregarás filas automáticamente.
3. **Conectarás Sheet → Slides → PDF → Gmail** - Segundo escenario que genera el reporte completo y lo envía a tu correo.
4. **Completarás el Desafío post-clase** - Nombre de PDF con fecha dinámica y error handler básico.

---

## Objetivos de Aprendizaje

Al finalizar esta clase, podrás:

1. **Explicar** los conceptos base de Make (escenario, módulo, operación, trigger, conexión) y la diferencia Instant vs Scheduled.
2. **Construir** un flujo Gmail → Sheet con Instant Trigger y filtro de asunto.
3. **Construir** un flujo Sheet → Slides → PDF → Gmail reemplazando ≥5 marcadores crudos y calculados.
4. **Agregar** mejoras básicas (nombre de archivo con fecha, error handler) como preparación para el Módulo 2.

---

## ✅ Preparación para la Clase

### De clases anteriores

- Sheet con 3 pestañas y rangos nombrados (Clase 2)
- Plantilla de Slides con ~18-20 marcadores documentados (Clase 3)
- Tabla de parámetros actualizada

### Reflexión previa

Antes de llegar a clase, reflexiona sobre:

- Si tu sistema estuviera funcionando hoy, ¿qué haría la diferencia más grande en tu trabajo semanal?
- ¿Qué correo sueles recibir con información que podría ir directamente a un Sheet si fuera automático?

### Herramientas

- [ ] **Cuenta de Make** - [make.com](https://make.com/){:target="_blank"} — crear cuenta gratuita antes de la clase
- [ ] **Sheet de Clase 2 y plantilla de Clase 3** - Listas y accesibles
- [ ] **Correo de prueba** - Puedes enviarte correos a ti mismo para probar el Instant Trigger

### Lectura sugerida

- [Make: Primer escenario](https://www.make.com/en/help/tools/create-your-first-scenario){:target="_blank"} - Tutorial oficial corto.
- [Make vs Zapier](https://www.make.com/en/help/tools/make-vs-zapier){:target="_blank"} - Comparación útil si ya usabas Zapier.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Escenario** | El flujo completo que construyes en Make (equivalente a "workflow" o "Zap"). |
| **Módulo** | Cada paso del flujo (leer Gmail, escribir en Sheet, exportar PDF). |
| **Operación** | Cada vez que un módulo ejecuta. Cuenta para el límite de 1,000/mes. |
| **Conexión** | Autenticación entre Make y tus cuentas (Gmail, Sheets). |
| **Trigger** | Módulo que inicia el flujo. |
| **Instant Trigger** | Se activa en 2-5 segundos cuando algo pasa. |
| **Scheduled Trigger** | Corre cada X tiempo (cada 15 min, diario, semanal). |
| **Replace Text** | Operación de Slides que busca `{{marcador}}` y lo sustituye. |

---

## Recursos Adicionales

- [Plan gratuito de Make](https://www.make.com/en/pricing){:target="_blank"} - Verifica límites y qué incluye.
- [Gmail Watch Emails en modo Instant](https://www.make.com/en/help/app/gmail){:target="_blank"} - Documentación del módulo que usarás.

---

> ⚠️ **Lab Calificado** - Este lab es la evaluación integradora del Módulo 1. Ver rúbrica en `lab/README.md`.
