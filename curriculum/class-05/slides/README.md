<!-- .slide: data-background="#0A192F" -->

# SESIÓN 5
## GEMINI API + DOS FLUJOS

Sistema modelo completo con IA funcionando

*2.5 horas · IA estratégica para Profesionales*

---

## QUÉ VAMOS A LOGRAR

*Aprendizaje esperado · Puntos clave · Evaluación*

### APRENDIZAJE ESPERADO

Integra la Gemini API gratuita en Make para extraer datos estructurados desde texto libre y deja funcionando dos flujos: recolección instantánea (correo → Gemini → Sheet) y reporte semanal (Sheet → Gemini → Slides → PDF).

### PUNTOS CLAVE

1. Obtener API key de Gemini gratuita
2. Extraer datos desde correos con IA
3. Generar insights con IA (marcadores tipo 3)
4. Cerrar flujo instantáneo con confirmación
5. Activar flujo semanal scheduled + Historico

### EVALUACIÓN

- Sistema modelo completo funcionando
- Flujo instantáneo activo
- Flujo semanal scheduled

---

## Apertura · 10 min

### Del texto libre al sistema activo

**01 · DEMO INICIAL**
Correo informal → JSON en 5 seg
Observa la magia de la IA.

**02 · TU META HOY**
Salir con sistema modelo completo
funcionando 24/7.

**03 · EXPERIENCIA**
¿Has escuchado de APIs?
Sí / No / Más o menos

---

## API, HTTP Y JSON

*El idioma que entiende Make con Gemini*

**15 min · Teoría**

- API = interfaz entre programas (analogía: mozo en restaurante)
- HTTP request POST → envías datos a Gemini
- Response → recibes la respuesta
- **API Key:** tu contraseña (nunca compartirla)
- **JSON:** estructura `{clave: valor}` y listas `[]`
- Plan gratuito Gemini: 1,500 requests/día

---

## OBTÉN + EXTRAE · API KEY Y EXTRACCIÓN CON GEMINI

*Configura Gemini API y convierte texto libre en JSON*

**45 min · Individual**

### QUÉ HACER

1. Google AI Studio → Get API key
2. En Make agrega módulo HTTP con la key
3. Modifica flujo sesión 4: Gmail → Gemini → Sheets
4. Prompt: extraer ventas en JSON estructurado
5. Prueba con 3 correos informales distintos

✓ **Verificación:** Correo informal → filas bien estructuradas en Sheet

---

## GENERA + CIERRA · INSIGHTS + FLUJO INSTANTÁNEO

*Gemini analiza datos y cierra la recolección con confirmación*

**40 min · Individual**

### QUÉ HACER

1. En flujo semanal: HTTP a Gemini con datos del Sheet
2. Prompt JSON: resumen, hallazgos, riesgos, oportunidad
3. Mapea cada campo al marcador de Slides
4. En flujo instantáneo: agrega confirmación al vendedor
5. Activa el flujo instantáneo (botón de activación)

✓ **Verificación:** Flujo instantáneo activo + insights generados

---

## ACTIVA · FLUJO SEMANAL SCHEDULED + HISTORICO

*Cierra el sistema modelo completo*

**30 min · Individual**

### QUÉ HACER

1. Cambia trigger manual a Scheduled viernes 4pm
2. Al final del flujo: Sheets — Add a row (Historico)
3. Asunto del correo generado por IA
4. Activa scheduled trigger
5. Run once para verificar funcionamiento completo

✓ **Verificación:** Sistema modelo completo: 2 flujos activos con IA

---

## SISTEMA MODELO COMPLETO FUNCIONANDO

*Los artefactos que construiste hoy*

**01** API key de Gemini configurada y funcionando

**02** Flujo instantáneo activo: recolección 24/7

**03** Flujo semanal scheduled: reporte automático cada viernes

**04** Todos los marcadores conectados (tipo 1, 2 y 3)

**05** Historico acumulándose solo

### PRÓXIMA SESIÓN

Sesión 6: Optimizamos prompts para storytelling de datos + mejores prácticas + definimos puntos de personalización para tu proyecto propio.
