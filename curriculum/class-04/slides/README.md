<!-- .slide: data-background="#0A192F" -->

# SESIÓN 4
## MAKE BÁSICO

Tu primer flujo automático con Instant Trigger

*2.5 horas · IA estratégica para Profesionales*

---

## QUÉ VAMOS A LOGRAR

*Aprendizaje esperado · Puntos clave · Evaluación*

### APRENDIZAJE ESPERADO

Construye flujos automáticos en Make usando Instant Trigger de Gmail conectando Sheets y Slides para entender módulos, triggers y rutas con actualización en tiempo real.

### PUNTOS CLAVE

1. Módulos, triggers, operaciones y conexiones
2. Instant Trigger de Gmail (2-5 segundos)
3. Conectar Gmail con Google Sheets
4. Conectar Sheets con Slides (Replace Text)
5. Exportar PDF y enviar por Gmail

### EVALUACIÓN

- Escenario 1: Gmail → Sheets (instant)
- Escenario 2: Sheets → Slides → PDF
- 5 marcadores tipo 1 y 2 funcionando

---

## Apertura · 10 min

### Prepárate para el efecto WOW

**01 · CUENTA LISTA**
¿Tienes cuenta gratuita de Make?
Levanta la mano si sí.

**02 · DEMO EN VIVO**
Correo enviado → Sheet actualizado
en 5 segundos. Observa.

**03 · TU SUEÑO**
¿Qué automatización personal harías?
Responde en chat.

---

## QUÉ ES MAKE Y SUS CONCEPTOS BASE

*Plataforma de automatización visual sin código*

**10 min · Teoría**

- Plan gratuito: 1,000 operaciones/mes
- **Escenario** = el flujo completo
- **Módulo** = cada paso del flujo
- **Operación** = cada ejecución (cuenta para el límite)
- **Conexión** = autenticación con tus apps
- **Trigger** = el módulo que inicia el flujo

---

## INSTANT VS SCHEDULED TRIGGER

*Dos formas de activar un flujo*

**10 min · Teoría**

- **Instant:** se activa al instante (2-5 segundos)
  → Recolección en tiempo real (efecto WOW en clase)
- **Scheduled:** corre cada X tiempo
  → Reporte periódico (viernes 4pm)

Este curso usa AMBOS

---

## CONECTA · GMAIL CON SHEETS (INSTANT)

*Primer flujo con reacción en tiempo real*

**40 min · Individual**

### QUÉ HACER

1. Crea escenario nuevo en Make
2. Gmail — Watch Emails en modo Instant
3. Filtro: asunto 'Ventas del día'
4. Agrega Google Sheets — Add a row
5. Prueba: envía correo y ve Sheet actualizar en segundos

✓ **Verificación:** Sheet con 3 filas agregadas automáticamente

---

## CONECTA · SHEETS CON SLIDES

*Flujo manual que genera el reporte*

**35 min · Individual**

### QUÉ HACER

1. Crea segundo escenario (Run once)
2. Sheets — Search Rows lee VentasSemanaActual
3. Slides — Create from Template (duplica)
4. Slides — Replace Text (3-5 marcadores)
5. Calcula tipo 2 con módulos Date/Math

✓ **Verificación:** Plantilla duplicada con valores reales

---

## ENVÍA · PDF POR GMAIL

*Cierra el flujo completo*

**25 min · Individual**

### QUÉ HACER

1. Slides — Export as PDF
2. Gmail — Send an Email
3. A tu propio correo con PDF adjunto
4. Run once del flujo completo
5. Verifica que el correo llega

✓ **Verificación:** PDF en tu bandeja con marcadores reemplazados

---

## LO QUE TE LLEVAS HOY

*Los artefactos que construiste hoy*

**01** 2 escenarios de Make funcionando

**02** Instant Trigger Gmail → Sheet en tiempo real

**03** Flujo manual Sheets → Slides → PDF → Gmail

**04** 5 marcadores tipo 1 y 2 reemplazados automáticamente

### PRÓXIMA SESIÓN

Sesión 5: Agregamos IA al flujo con Gemini API y dejamos los DOS flujos completos funcionando. Fin de la Fase 1, inicio de Fase 2.
