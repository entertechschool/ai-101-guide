> **Módulo 1:** Clase 2 de 4

# Clase 02: Google Sheets con IA

## Resumen

Hoy construirás la fuente de datos de tu sistema automatizado. No vas a abrir un Sheet en blanco: vas a usar a tu Gem como copiloto para diseñar la estructura correcta desde el primer intento. La diferencia entre un Sheet que "funciona para ver" y uno que "funciona para automatizar" está en tres decisiones: qué pestañas tiene, cómo están nombradas las columnas y qué rangos nombrados defines.

Al terminar vas a tener un Google Sheet con tres pestañas — operación, configuración e histórico — listas para que en la Clase 4 se conecten automáticamente con Make y en la Clase 5 reciban datos de correos procesados por IA. También vas a iniciar la **tabla de parámetros**, un documento vivo que acumula decisiones y te acompaña hasta el Demo Day.

---

## ¿Por qué te sirve?

- **Automatizar sobre datos mal estructurados multiplica los errores por 10.** Make y Gemini necesitan columnas consistentes y pestañas separadas — sin eso, cualquier sistema falla.
- **Un rango nombrado bien definido hace que tu sistema sobreviva a cambios de layout.** Agregar columnas, reordenar filas o renombrar pestañas deja de romper tu flujo.
- **Separar datos operativos de configuración ahorra semanas cuando quieras ajustar metas o agregar miembros al equipo.** Los parámetros del negocio viven aparte y los editas sin tocar el flujo.

---

## 🎯 ¿Qué haremos en clase?

1. **Exploraremos por qué la IA necesita estructura** - Descubrirás la diferencia entre datos para mirar y datos para automatizar.
2. **Diseñarás la pestaña de operación** - Usarás tu Gem para proponer columnas y generar 15 filas de ejemplo.
3. **Construirás la pestaña de configuración** - Capturarás los parámetros del negocio (metas, equipo, categorías) en un solo lugar.
4. **Cerrarás con la pestaña histórica y rangos nombrados** - Dejarás el Sheet listo para que Make lo lea sin riesgo.

---

## Objetivos de Aprendizaje

Al finalizar esta clase, podrás:

1. **Explicar** por qué la automatización requiere datos estructurados y no texto libre.
2. **Diseñar** un Google Sheet con 3 pestañas (operación, configuración, histórico) con propósitos claros.
3. **Generar** 15 filas de datos de ejemplo usando Gemini para probar la estructura.
4. **Definir** rangos nombrados en Google Sheets y documentarlos en la tabla de parámetros.

---

## ✅ Preparación para la Clase

### De clases anteriores

- Gem asistente del curso funcionando (Clase 1)
- Brief del proyecto de instrucción en Google Doc
- Carpeta "Proyecto de Instrucción" en Google Drive

### Reflexión previa

Antes de llegar a clase, reflexiona sobre:

- ¿Qué datos manejas cada semana y cómo los tienes organizados hoy (Excel, papel, Notion, cabeza)?
- ¿Qué información te cuesta más consolidar cuando llega el momento de armar tu reporte?

### Herramientas

- [ ] **Google Sheets** - Accesible desde [sheets.google.com](https://sheets.google.com/){:target="_blank"} con tu cuenta de Google
- [ ] **Gem del curso** - Ya configurado en la Clase 1 con tu brief y archivo de referencia
- [ ] **Tabla de parámetros** - La iniciarás en esta clase (Google Doc nuevo)

### Lectura sugerida

- [Rangos con nombre en Google Sheets](https://support.google.com/docs/answer/63175){:target="_blank"} - Guía oficial de Google.
- [Buenas prácticas para Sheets que se automatizan](https://developers.google.com/sheets/api/guides/concepts){:target="_blank"} - Conceptos de cómo ven las APIs un Sheet.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Datos estructurados** | Información organizada en tabla con columnas consistentes, lista para ser procesada automáticamente. |
| **Pestaña operativa** | Donde llegan los datos del día a día (nombre sugerido: `VentasSemanaActual`). |
| **Pestaña de configuración** | Parámetros del negocio que no cambian (metas, vendedores, categorías). |
| **Pestaña histórica** | Memoria acumulada semana a semana para comparar y detectar tendencias. |
| **Rango nombrado** | Apodo para un rango de celdas (ej: `RangoVentas` = `VentasSemanaActual!A:G`). |
| **Tabla de parámetros** | Documento vivo del curso que registra columnas, rangos, marcadores y decisiones. |

---

## Recursos Adicionales

- [Plantillas de Google Sheets](https://docs.google.com/spreadsheets/u/0/?ftv=1){:target="_blank"} - Galería oficial, útil para ver ejemplos de estructura.
- [Fórmulas básicas de Google Sheets](https://support.google.com/docs/table/25273){:target="_blank"} - Referencia rápida para SUMA, BUSCARV, CONTAR.SI.
