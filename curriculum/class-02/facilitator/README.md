# Guía del Facilitador - Clase 02: Google Sheets con IA

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Datos estructurados**: información en tabla con columnas consistentes; lo contrario es texto libre en WhatsApp/correo.
- **Pestaña operativa**: donde llegan los datos del día a día; crece constantemente.
- **Pestaña de configuración**: parámetros del negocio que cambian raro (meta, equipo).
- **Pestaña histórica**: memoria semanal para comparar; crece una fila por período.
- **Rango nombrado**: apodo para un rango que sobrevive a cambios de layout; Make los usa en lugar de `A1:G50`.

---

## 🔗 Analogías Útiles

**3 pestañas <> cocina profesional:**
Operativa = mesa de trabajo (pasa de todo). Config = recetario (casi no se toca). Histórico = libro de servicios dados (consulta eventual). Si mezclás las 3 en la misma mesa, nada funciona.

**Rango nombrado <> contacto del teléfono:**
`A1:G50` es como marcar el número entero cada vez. `RangoVentas` es como "Mamá" — si cambia de número, actualizás un contacto y todo sigue funcionando.

**Columna Descripción <> nota al pie de cada dato:**
El vendedor puso "S/ 2,800". La Descripción cuenta el "por qué" (renovación grande, cliente nuevo). En la Clase 5, Gemini usa esa Descripción para generar insights de verdad — sin ella, el reporte dice cifras pero no historias.

---

## 📚 Contexto Histórico / Contexto Actual

### Google Sheets: por qué es la capa de datos ideal para no-code

Sheets nació en 2006 como respuesta a Excel en la nube. En 2020-2024 se volvió la capa de datos favorita del no-code: Zapier, Make, Airtable y cientos de herramientas integran con Sheets porque el 90% de pymes ya lo usan. Para AI 101, tiene la ventaja de que no requiere aprender bases de datos — el estudiante ya sabe usarlo.

> **Para contar en clase:** "Aprendiste Google Sheets para hacer tablas. Hoy aprendes a diseñarlo para que otras herramientas lo lean sin quebrarse."

### Rangos nombrados: por qué importan en automatización

En 2022-2023, Make (y Zapier) popularizaron leer Sheets por rango nombrado en lugar de coordenadas. El efecto: un Sheet con 10 años de historial sigue funcionando con el mismo flujo. Sin rangos nombrados, cada cambio de columna rompe el sistema.

> **Para contar en clase:** "Si tu Sheet crece 5 años y tu sistema no usa rangos nombrados, vas a romper todo cada vez que quieras agregar una métrica."

**Fuentes:** [Google Sheets: Rangos con nombre](https://support.google.com/docs/answer/63175){:target="_blank"}, [Make University: Google Sheets best practices](https://academy.make.com/){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "¿Por qué separar parámetros del negocio (meta, equipo) en una pestaña distinta a los datos operativos? ¿Qué problema se evita?"

**Respuesta esperada:** Evita tener que editar la misma columna en 50 filas cuando cambia la meta; centraliza decisiones.

**Script post-respuestas:**
```
Facilitador: "Exacto. Si tu meta semanal está escrita en 50 filas, cambiarla es una tortura.
Si vive en una sola celda de Config, cambia una vez y todo se recalcula. Eso es diseño para automatización."
```

### Demo Principal

**Qué mostrar:** el Sheet del caso Roberto en vivo — primero mal diseñado (1 pestaña todo junto), luego rediseñado con las 3 pestañas y un rango nombrado.

**Script sugerido:**
```
Facilitador: "Aquí tengo el Sheet como lo haría alguien sin este curso: todo en una sola pestaña."
[Muestra Sheet con columnas mezcladas: ventas + meta + historial todo junto]
Facilitador: "¿Qué problema ven? Si quiero cambiar la meta, tengo que editar 200 filas."
[Abre versión con 3 pestañas]
Facilitador: "Ahora la meta vive en Config, celda B2. Un cambio, todo se recalcula."
```

**Plan B (si Sheets se cae o no conecta):** tener screenshots de ambas versiones listos en una slide.

### Transición al Lab

**Momento crítico:** los estudiantes se bloquean si su brief no encaja 100% con el caso Roberto (no tienen "ventas" sino "clases" o "pacientes").

**Script sugerido:**
```
Facilitador: "Si su caso no son ventas, no pasa nada. Reemplacen:
VentasSemanaActual → CampanasSemanaActual, o CohortesSemana, o PacientesSemana.
El patrón es [Entidad]SemanaActual. Las columnas serán distintas a las mías, eso lo resuelve su Gem."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Revisión cruzada de 2 minutos"

Contexto: después de Actividad 1, antes de Config.

Cada estudiante le muestra al vecino las 7 columnas de su pestaña operativa. El vecino le pregunta "¿por qué esa columna?". Si el estudiante no sabe responder, la columna probablemente no sirve.

```
Facilitador: "Roten con el vecino. 1 minuto cada uno.
Pregunta única: '¿Para qué usa el reporte esa columna?'
Si no sabe responder, vuelven a Gemini y refinan."
```

### Dinámica 2: "¿Config o Operativa?"

Contexto: durante la teoría, para consolidar la diferencia.

Lanzás datos al aire y el grupo grita "Config" u "Operativa":

```
Facilitador: "Nombre del vendedor Juan" → Config
Facilitador: "Venta de S/ 1,500 del martes" → Operativa
Facilitador: "Meta del mes" → Config
Facilitador: "Cliente nuevo que compró" → Operativa
Facilitador: "Tipo de producto Premium" → Depende (si es catálogo fijo, Config)
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Prompt para columnas operativas (caso genérico)

**Cuándo usarlo:** si un estudiante dice "mi Gem no entiende qué columnas necesito".

```
Según mi brief, necesito la pestaña operativa donde se registrarán
los datos del día a día de mi reporte. Dame una tabla con columnas
mínimas, tipo de dato, y justifica por qué cada una. Incluye una
columna "Descripción" para contexto en texto libre.
```

**Tip:** la columna Descripción es crítica. Es la que Gemini usa en la Clase 5 para generar insights — sin ella, el reporte de Clase 7 saldrá plano.

### Ejemplo 2: Prompt para generar filas de ejemplo realistas

**Cuándo usarlo:** cuando al estudiante le da pereza escribir 15 filas a mano.

```
Genera 15 filas de datos de ejemplo realistas para la pestaña
VentasSemanaActual con las columnas [lista columnas]. Varía fechas
en los últimos 7 días, usa nombres de vendedores reales, montos
realistas para [industria], y descripciones diversas.
Formato: TSV (separado por tabulaciones).
```

**Tip:** TSV es mejor que CSV porque pega directo en Sheets sin importar comas en los textos.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Mi Sheet tiene una sola pestaña con todo" | No separó operativa/config/histórico | Mostrar demo del Sheet de Roberto mal y bien diseñado |
| "Las columnas son genéricas (Col1, Col2)" | El Gem no tiene suficiente contexto del brief | Pedir que revisen que el brief esté cargado en las instrucciones del Gem |
| "No entiendo qué va en Historico" | Confunde con operativa | Historico tiene 1 fila por semana (resumen); operativa tiene 1 fila por transacción |
| "Mi rango nombrado apunta a `A1:G50`" | Usó coordenadas fijas | Reemplazar con `A:G` (columna completa sin límite de fila) |
| "No aparece la opción Rangos con nombre" | Google cambió el menú | Está en **Datos → Rangos con nombre** o busca "nombre" en el menú de búsqueda |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Puede explicar por qué Config y Operativa son pestañas distintas con un ejemplo de su trabajo
- Nombra sus rangos con palabras descriptivas (`RangoVentas`, no `Rango1`)
- Adapta el patrón del caso Roberto a su caso sin copiar literal

### El estudiante NECESITA AYUDA cuando:
- Tiene todos los datos en una sola pestaña
- Los nombres de columnas son genéricos ("Dato", "Info", "Campo")
- No sabe qué métrica guardar en Historico

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura terminada | 3 preguntas respondidas en chat | Avanzar con la respuesta del que sí haya respondido |
| 25 | Teoría terminada | Quiz Pre-Lab respondido | Tomar 1-2 respuestas y seguir |
| 65 | Actividad 1 | Pestaña operativa con 15 filas generadas por Gemini | Si no salen filas, ofrecer TSV pre-hecho del caso Roberto |
| 90 | Actividad 2 | Pestaña Config con 4+ parámetros reales | Si tienen dudas, escribir los 4 parámetros en conjunto |
| 125 | Actividad 3 | 3 rangos nombrados visibles | Pedir captura del menú Datos → Rangos con nombre |
| 150 | Cierre | Tabla de parámetros con columnas/rangos/config registrados | Revisar que Doc existe |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Preguntar por casos específicos: "¿Quién no tiene ventas como métrica? ¿Tú qué mides?"
- Compartir el Sheet del caso Roberto en pantalla compartida para que copien estructura.

### Si alguien domina la conversación:
- "Excelente caso — guardémoslo para la Clase 7 donde adaptás tu sistema propio."

### Si la mayoría termina antes:
- Logro 🟢 (validación de datos) o 🟡 (gráfico dinámico).

### Si la mayoría se atrasa:
- Reducir a 10 filas de ejemplo en vez de 15.
- Omitir pestaña Historico y dejar solo placeholder vacío con las columnas; la llenan en la Clase 4.

### Si hay preguntas fuera de alcance:
> "Buena pregunta. Eso lo vemos en Clase 4 cuando Make lee el Sheet."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logro 🔴: diseñar fórmulas que preparen el llenado automático del Historico (preview de Clase 5).
- Pedir que agreguen validación de datos a la columna Tipo.

### Para estudiantes con dificultades:
- Usar el Sheet del caso Roberto como plantilla (ofrecer link al Sheet modelo).
- Sentarse con ellos 5 min durante Actividad 3 para configurar los 3 rangos juntos.

---

## ❓ Preguntas Frecuentes

### P: ¿Por qué usar Google Sheets y no Excel?
**R:** Porque Make y Gemini tienen integración nativa con Google (sin configuración extra). Si ya trabajan en Excel, pueden seguir — pero el flujo del curso asume Google.

### P: ¿Mi Sheet puede ser privado o tiene que ser compartido?
**R:** Privado. Make pide permisos de tu cuenta de Google para leerlo, pero nadie más lo ve.

### P: ¿Cuántas columnas máximo en la pestaña operativa?
**R:** Idealmente 8-10. Más de 15 es señal de que mezclaste operativa con histórico o config.

### P: ¿Cuándo llenamos Historico de verdad?
**R:** Clase 5 (con IA) lo llena automáticamente cada vez que corre el flujo semanal.

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| 01 | Gem asistente | Ahora es copiloto de diseño: le pedís estructura, no solo texto |
| 01 | Brief del proyecto | Las columnas del Sheet responden al brief |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase diseñamos la plantilla de Slides del reporte. Los marcadores que vamos a nombrar (`{{ventas_total}}`, `{{clientes_nuevos}}`) se van a conectar a las columnas de este Sheet. Lo que hicieron hoy es la base de los datos que Slides va a mostrar."

**Pre-work / Tarea implícita:** llenar las 15 filas de ejemplo con datos más cercanos a su realidad (si las generadas por Gemini son muy genéricas).

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes lograron las 3 pestañas + 3 rangos nombrados?
- ¿Quiénes tenían casos muy distintos al Roberto? (candidatos a preview personalizado en Clase 7)
- ¿Algún estudiante no tiene datos históricos reales? (seguimiento para que inventen datos simulados antes de Clase 4)
- ¿La tabla de parámetros quedó iniciada en todos?
