> **Módulo 1:** Clase 3 de 4

# Clase 03: Google Slides con IA

## Resumen

Un reporte ejecutivo no es un documento — es una **plantilla** con partes fijas y marcadores variables que se reemplazan cada vez que el sistema corre. Hoy vas a diseñar esa plantilla para el reporte de tu proyecto de instrucción. Vas a usar tu Gem para proponer las 6 secciones clásicas, nombrar cada marcador variable con convenciones claras y clasificarlos por tipo: unos vienen del Sheet (crudos), otros los calcula Make (calculados) y otros los genera Gemini (generados por IA).

Al terminar, tu plantilla de Slides estará lista para que en la Clase 4 Make reemplace los marcadores automáticamente con datos reales. La tabla de parámetros que iniciaste la Clase 2 va a crecer con ~18-20 marcadores documentados — es la pieza de información más importante que construyes en el Módulo 1.

---

## ¿Por qué te sirve?

- **Los reportes profesionales tienen 80% de estructura fija y 20% de datos variables.** Diseñar esa estructura una sola vez ahorra 2-4 horas cada vez que toca armar un reporte.
- **Un marcador bien nombrado es documentación viva del sistema.** Leer `{{ventas_total_semana}}` en una plantilla deja claro qué es, de dónde viene y qué esperar — sin abrir ningún otro archivo.
- **Clasificar marcadores por tipo (crudo/calculado/IA) es el mapa que guía todas las decisiones del Módulo 2.** En la Clase 5 sabrás exactamente qué prompt escribir para cada marcador tipo IA, y qué fórmula para los calculados.

---

## 🎯 ¿Qué haremos en clase?

1. **Exploraremos la anatomía de un reporte ejecutivo** - Descubrirás las 6 secciones clásicas y la regla "1 slide = 1 idea".
2. **Diseñarás tu plantilla con 6 slides** - Usarás tu Gem para proponer secciones según tu brief y aplicarás paleta y jerarquía.
3. **Nombrarás todos los marcadores** - Aplicarás convención `snake_case`, los clasificarás por tipo y los registrarás en la tabla de parámetros.
4. **Probarás la plantilla manualmente** - Reemplazarás 3-4 marcadores con datos reales para ver cómo se verá el reporte final.

---

## Objetivos de Aprendizaje

Al finalizar esta clase, podrás:

1. **Describir** las 6 secciones clásicas de un reporte ejecutivo y qué pertenece a cada una.
2. **Clasificar** marcadores variables en 3 tipos (crudo, calculado, generado por IA) según su origen.
3. **Diseñar** una plantilla de Slides con marcadores en convención `snake_case` alineada a la tabla de parámetros.
4. **Validar** visualmente la plantilla reemplazando marcadores con datos de prueba.

---

## ✅ Preparación para la Clase

### De clases anteriores

- Google Sheet con 3 pestañas y datos de ejemplo (Clase 2)
- Tabla de parámetros con columnas y rangos nombrados registrados
- Gem del curso funcionando con brief y archivo de referencia

### Reflexión previa

Antes de llegar a clase, reflexiona sobre:

- Si tuvieras que describir tu reporte actual en 6 secciones, ¿cuáles serían?
- ¿Qué partes del reporte cambian semana a semana y cuáles son siempre iguales?

### Herramientas

- [ ] **Google Slides** - Accesible desde [slides.google.com](https://slides.google.com/){:target="_blank"}
- [ ] **Tu Sheet con 3 pestañas** - De la Clase 2
- [ ] **Tabla de parámetros** - Google Doc iniciado en la Clase 2 (va a crecer hoy)

### Lectura sugerida

- [Storytelling con datos](https://www.storytellingwithdata.com/blog/2013/04/what-it-means-to-be-a-data-driven-organization){:target="_blank"} - Principios básicos de reportes efectivos.
- [Reemplazar texto en Google Slides](https://support.google.com/docs/answer/6317504){:target="_blank"} - Referencia de la función Replace Text que Make usará en Clase 4.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Marcador variable** | Texto en la plantilla (tipo `{{nombre}}`) que Make reemplaza por un valor. |
| **Marcador crudo (tipo 1)** | Viene directo de una celda del Sheet. Ej: `{{ventas_total}}`. |
| **Marcador calculado (tipo 2)** | Make lo calcula con fórmula. Ej: `{{variacion_pct}}`. |
| **Marcador de IA (tipo 3)** | Gemini lo genera analizando datos. Ej: `{{hallazgo_1}}`. |
| **snake_case** | Convención: todo minúsculas, palabras separadas por guion bajo (`ventas_total_semana`). |
| **Replace Text** | Operación de Slides que busca `{{marcador}}` y lo sustituye por un valor. |

---

## Recursos Adicionales

- [Google Slides: inserción de gráficos vinculados](https://support.google.com/docs/answer/7009814){:target="_blank"} - Para el gráfico vinculado al Sheet.
- [Paletas de colores para reportes ejecutivos](https://coolors.co/palettes/trending){:target="_blank"} - Referencia visual si no tienes paleta propia.
