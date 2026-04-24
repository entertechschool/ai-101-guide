> **Módulo 2:** Clase 1 de 4

# Clase 05: Gemini API + 2 flujos completos

## Resumen

Esta es la **clase bisagra** del curso. Hasta ahora construiste el sistema sin IA — piezas conectadas con Make que mueven datos. Hoy la IA entra al flujo. Vas a conectar **Gemini API** directamente a los escenarios de Make, y los marcadores tipo 3 (`{{hallazgo_1}}`, `{{resumen_ejecutivo}}`) que estaban vacíos empezarán a llenarse con insights contextuales generados en segundos.

Al terminar, el sistema modelo está completo: un flujo instantáneo que convierte correos informales en filas estructuradas del Sheet, y un flujo scheduled semanal que lee todo, genera insights con Gemini, llena la plantilla, exporta PDF y lo manda por correo. Todo activo 24/7, consumiendo el plan gratuito de Gemini (1,500 requests/día — más que suficiente).

---

## ¿Por qué te sirve?

- **La API gratuita de Gemini da 1,500 requests por día.** Para un reporte semanal con ~15 llamadas, eso son meses de uso sin costo.
- **Un correo informal se convierte en datos estructurados en 5 segundos.** Adiós a pedirle formatos rígidos a tu equipo — Gemini extrae lo importante sin importar cómo lo escribieron.
- **El mismo JSON llena 10 marcadores del Slides con una sola llamada a Gemini.** Eficiencia de operaciones de Make + coherencia del output.

---

## 🎯 ¿Qué haremos en clase?

1. **Exploraremos qué es una API y cómo funciona HTTP/JSON** - Descubrirás el lenguaje que Make usa para hablar con Gemini.
2. **Configurarás tu API key de Gemini** - Obtendrás credenciales gratuitas y las conectarás al módulo HTTP de Make.
3. **Agregarás IA al flujo instantáneo** - Gemini convertirá correos informales en filas bien estructuradas del Sheet.
4. **Activarás el flujo scheduled semanal** - Gemini generará los insights tipo 3 y alimentará el Historico automáticamente.

---

## Objetivos de Aprendizaje

Al finalizar esta clase, podrás:

1. **Explicar** qué son API, HTTP POST y JSON con analogías propias.
2. **Obtener** una API key de Gemini gratuita y configurarla en el módulo HTTP de Make.
3. **Construir** un prompt JSON que Gemini responde con datos estructurados para marcadores tipo 3.
4. **Activar** los dos escenarios del sistema modelo (instantáneo + scheduled) y verificar ciclo completo end-to-end.

---

## ✅ Preparación para la Clase

### De clases anteriores

- Los 2 escenarios de Make del Módulo 1 funcionando (Clase 4)
- Sheet con 3 pestañas recibiendo filas vía Instant Trigger
- Plantilla de Slides con marcadores tipo 3 nombrados (vacíos, se llenarán hoy)
- Tabla de parámetros actualizada

### Reflexión previa

Antes de llegar a clase, reflexiona sobre:

- Cuando lees un correo informal de un vendedor, ¿qué datos "extraes" mentalmente? Eso es lo que Gemini va a hacer.
- De los marcadores tipo 3 de tu plantilla, ¿cuál te da más curiosidad ver generado por IA?

### Herramientas

- [ ] **API Key de Gemini** - Obtenerla en [Google AI Studio](https://aistudio.google.com/apikey){:target="_blank"} antes de la clase (gratis, usa tu cuenta de Google)
- [ ] **Cuenta de Make** con los 2 escenarios de Clase 4
- [ ] **3-5 correos de prueba** con texto informal (como los que reciben tus vendedores/clientes/colaboradores)

### Lectura sugerida

- [Documentación de Gemini API](https://ai.google.dev/gemini-api/docs){:target="_blank"} - Referencia oficial.
- [Módulo HTTP en Make](https://www.make.com/en/help/tools/http){:target="_blank"} - Cómo hacer llamadas API genéricas.

---

## Glosario

| Término | Definición |
|---------|------------|
| **API** | *Application Programming Interface* — forma en que un programa habla con otro. Analogía: mozo en restaurante. |
| **API Key** | Contraseña única que te identifica ante Gemini API. **Nunca la compartas**. |
| **HTTP POST** | Método de envío de datos a una API (como enviar un formulario). |
| **JSON** | Formato de datos `{clave: valor}` que APIs entienden universalmente. |
| **Módulo HTTP en Make** | Módulo genérico para llamar cualquier API con URL, headers y body. |
| **Rate limit** | Límite de llamadas por día/minuto. Gemini free: 1,500 requests/día, 15/min. |
| **SystemPrompt** | Instrucciones base que definen el comportamiento de Gemini en cada llamada. |

---

## Recursos Adicionales

- [Google AI Studio Playground](https://aistudio.google.com/){:target="_blank"} - Experimenta con prompts antes de llevarlos a Make.
- [Límites del plan gratuito](https://ai.google.dev/pricing){:target="_blank"} - Detalle de rate limits y cuotas.
