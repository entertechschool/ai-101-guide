# Guía del Facilitador - Clase 03: Google Slides con IA

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Plantilla con marcadores**: estructura fija con huecos nombrados que Make llenará automáticamente.
- **Marcador crudo (tipo 1)**: sale directo de una celda del Sheet; Make hace Search + Replace Text.
- **Marcador calculado (tipo 2)**: Make calcula con fórmula/módulo (Date, Math); luego Replace Text.
- **Marcador generado por IA (tipo 3)**: Gemini lo produce en Clase 5; hoy queda nombrado y vacío.
- **snake_case**: convención (`ventas_total_semana`) que Replace Text soporta sin problemas.

---

## 🔗 Analogías Útiles

**Plantilla con marcadores <> formulario legal en papel:**
Los contratos tienen huecos marcados donde escribís el nombre del cliente, la fecha, el monto. El contrato es la plantilla; los huecos son los marcadores. Make es la mano que llena los huecos.

**3 tipos de marcadores <> 3 fuentes de información en un noticiero:**
Crudo = dato en la pantalla del productor (cotización, hora). Calculado = estadística derivada (variación vs ayer). IA = comentario del analista (explica el movimiento). Cada uno tiene origen distinto pero van en el mismo noticiero.

**Tabla de parámetros <> manual de referencia del sistema:**
Si mañana alguien más del equipo tiene que modificar el sistema, no necesita leer tu Make — lee la tabla de parámetros y sabe qué marcador existe, de dónde viene y qué contiene.

---

## 📚 Contexto Histórico / Contexto Actual

### Reportes con marcadores: por qué es el patrón estándar

En las agencias de reportería y en herramientas como Looker Studio, PowerPoint con plugins, Canva, se usa el mismo patrón hace 15 años: una plantilla fija + datos que se reemplazan. Make con Google Slides trajo ese patrón a no-code en 2021-2022, y hoy es la forma más simple de generar PDFs reportables automáticamente.

> **Para contar en clase:** "Lo que hacen las grandes agencias con software de $500/mes, ustedes lo hacen gratis con Google Slides + Make."

### La columna Descripción del Sheet: la mina de oro de los insights

En la Clase 2 los estudiantes agregaron una columna "Descripción" en `VentasSemanaActual`. Parece trivial, pero es donde Gemini hace su magia en la Clase 5: lee todas las descripciones de la semana y genera los marcadores tipo IA (hallazgos, riesgos, oportunidades). Sin Descripción, los hallazgos son tibios.

> **Para contar en clase:** "La diferencia entre un reporte que dice cifras y uno que cuenta historias está en esa columnita que agregamos la clase pasada."

**Fuentes:** [Make: Google Slides módulos](https://www.make.com/en/integrations/google-slides){:target="_blank"}, [Google Workspace: Docs + Slides templates](https://support.google.com/a/answer/6283553){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "Si tuvieras que dividir tu reporte actual en 'partes que cambian siempre' vs 'partes que siempre son iguales', ¿cuáles serían las partes que cambian?"

**Respuesta esperada:** La fecha, los números, los nombres de clientes, las conclusiones del período.

**Script post-respuestas:**
```
Facilitador: "Exacto — lo que acaban de decir son los marcadores variables.
Las partes que no cambian forman la plantilla. Hoy diseñamos ambas por separado."
```

### Demo Principal

**Qué mostrar:** la plantilla del caso Roberto con marcadores `{{...}}` visibles + demo rápida en Slides de cómo Replace Text reemplaza un marcador.

**Script sugerido:**
```
Facilitador: "Miren esta slide de Resumen del reporte de Roberto."
[Muestra slide con {{ventas_total}}, {{variacion_pct}}, {{resumen_ejecutivo}}]
Facilitador: "¿Ven los tres marcadores? Cada uno viene de un lugar distinto."
[Explica: ventas_total = Sheet. variacion_pct = Make. resumen = Gemini]
Facilitador: "En 2 clases todos se llenarán solos. Hoy los nombramos."
```

**Plan B (si Google Slides no carga):** pantalla compartida con capturas previas de la plantilla de Roberto.

### Transición al Lab

**Momento crítico:** los estudiantes se bloquean si quieren nombrar "perfectamente" los marcadores. Tenés que darles permiso de iterar.

**Script sugerido:**
```
Facilitador: "No busquen nombres perfectos. Busquen nombres claros.
`{{hallazgo_1}}` es mejor que `{{h1}}`, pero `{{principal_insight_comercial_de_la_semana}}` es peor.
Si dudan, empecen simple y después refinan en la Clase 6."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Clasifica en 10 segundos"

Contexto: durante la teoría, para consolidar tipos de marcadores.

Lanzás marcadores y el grupo grita el tipo:

```
Facilitador: "{{meta_semanal}}" → Crudo (del Sheet, celda Config)
Facilitador: "{{ventas_vs_meta_pct}}" → Calculado (Make: ventas/meta)
Facilitador: "{{recomendacion_gerencial}}" → IA (Gemini analiza)
Facilitador: "{{nombre_top_vendedor}}" → Crudo (Sheet) o Calculado (Make max)
```

### Dinámica 2: "Prueba manual cruzada"

Contexto: al final de Actividad 3.

Cada estudiante intercambia plantilla con el vecino. El vecino elige 3 marcadores y los reemplaza con datos inventados (en la plantilla prestada). Si el diseño aguanta, el nombre es claro. Si el vecino duda de qué poner, el nombre no es suficientemente descriptivo.

```
Facilitador: "Roten con el vecino. 3 minutos cada uno.
Si no sabés qué poner en `{{x}}`, el nombre no es claro. Anótalo.
Al final, cada uno recibe feedback de qué renombrar."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Prompt para las 6 secciones (caso Roberto)

**Cuándo usarlo:** cuando un estudiante pregunta "¿qué pongo en mis 6 secciones?"

```
Según mi brief (reporte semanal de ventas para gerente), dame las 6
secciones de mi reporte ejecutivo. Para cada sección: nombre, propósito
(1 línea), y qué información debería mostrar.
```

**Tip:** la "Portada" suele ser obviada — recordar que lleva contexto (fecha, nombre de empresa, período).

### Ejemplo 2: Nombres de marcadores bien formados (caso genérico)

**Cuándo usarlo:** cuando un estudiante duda de la convención.

```
{{portada_titulo}}           # agrupado por sección
{{portada_fecha_reporte}}    # prefijo portada_
{{resumen_ventas_total}}     # prefijo resumen_
{{hallazgo_1_texto}}         # numerado 1, 2, 3
{{riesgo_1_descripcion}}     # subíndice descripcion para claridad
{{accion_1}}                 # corto porque todo va en esa celda
```

**Tip:** el prefijo por sección sirve para buscar rápido en la tabla de parámetros cuando sean 20+ marcadores.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No sé qué marcadores debería tener" | No identifica qué es variable | Mostrar reporte viejo suyo y preguntar "¿qué cambia aquí cada semana?" |
| "Tengo 8 marcadores, no 18" | Se quedó en titulares, no llegó a detalles | Revisar slide por slide: cada sección suele tener 2-4 marcadores |
| "{{variación %}}" con tilde y símbolo | Caracteres especiales rompen Replace Text | Cambiar a `{{variacion_pct}}` |
| "Mi gráfico es imagen estática" | Insertó como imagen, no vinculado | Insertar → Gráfico → Desde Hojas de cálculo |
| "No sé si mi marcador es crudo o calculado" | Confunde origen de datos | Regla: si existe como celda única en el Sheet → crudo; si se calcula con 2+ datos → calculado |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Nombra marcadores en snake_case sin que le recuerdes
- Distingue crudo/calculado/IA sin dudar
- Agrupa marcadores por sección con prefijo consistente

### El estudiante NECESITA AYUDA cuando:
- Todos sus marcadores son tipo "crudo" (no identifica lo calculado ni lo IA)
- Sus nombres tienen espacios o mayúsculas
- No entiende por qué nombrar algo que hoy está vacío

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura terminada | Reporte modelo mostrado + reacción grupal | Avanzar si hay comentarios |
| 25 | Teoría terminada | Los 3 tipos de marcadores comprendidos (dinámica "Clasifica en 10 segundos") | Hacer 2-3 rondas extra de la dinámica |
| 60 | Actividad 1 | 6 slides con títulos y estilo | Si no llegan a 6, priorizar Portada, Resumen, Hallazgos |
| 105 | Actividad 2 | Tabla de parámetros con 18-20 marcadores | Si solo tienen 10-12, revisar qué sección está pobre |
| 135 | Actividad 3 | Marcadores insertados + prueba manual | Si no probaron, pedir que reemplacen 2 marcadores en vivo |
| 150 | Cierre | Revisión por pares exitosa | — |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Mostrar tu propia plantilla (como facilitador) y pedir "¿qué marcador le agregarían?"
- Pedir que 2 estudiantes compartan pantalla con su plantilla al mismo tiempo.

### Si alguien domina la conversación:
- Pedirle que ayude a un compañero con dudas (mentoría cruzada).

### Si la mayoría termina antes:
- Logro 🟡 (slide de apéndice con marcadores adicionales).

### Si la mayoría se atrasa:
- Reducir objetivo a 12-15 marcadores (en vez de 18-20). La clase 5 los puede pedir agregar más.
- Saltar la revisión por pares del cierre y hacer cierre individual.

### Si hay preguntas fuera de alcance:
> "Buena pregunta. Replace Text lo vemos Clase 4; insights con Gemini los llenamos Clase 5."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logro 🔴 (versión móvil de la plantilla para WhatsApp).
- Pedir que diseñen 25+ marcadores (incluyendo apéndice y metadata).

### Para estudiantes con dificultades:
- Ofrecer la plantilla modelo de Roberto como punto de partida para duplicar.
- Ayudarlos a nombrar los primeros 5 marcadores y que completen los siguientes solos.

---

## ❓ Preguntas Frecuentes

### P: ¿Los marcadores tienen que ser exactamente `{{x}}` con llaves dobles?
**R:** Sí. Las llaves dobles son la convención que reconocen las herramientas. `<x>` o `[x]` funcionarían pero no son estándar.

### P: ¿Qué pasa si nombro 2 marcadores igual?
**R:** Replace Text reemplaza todos los que coincidan — así que si ponés `{{nombre}}` en 2 slides, ambos reciben el mismo valor. Útil para títulos que se repiten; problemático si querías valores distintos.

### P: ¿Puedo usar imágenes como marcadores?
**R:** Sí, pero no con Replace Text directamente. En la Clase 5 aprenderán a usar "Replace Image" para el logo/gráficos, pero hoy es texto.

### P: ¿Cuántos marcadores es demasiado?
**R:** 25 está bien. Más de 30 empieza a ser frágil (más puntos de falla). Si tenés más, probablemente hay marcadores redundantes (ej: `{{total_ventas}}` y `{{ventas_total}}` duplicados).

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| 01 | Gem asistente | Sugiere las 6 secciones según el brief |
| 02 | Sheet con 3 pestañas | Los marcadores crudos vienen de VentasSemanaActual y Config |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase es la primera vez que conectamos todo. Construimos 2 flujos en Make: uno que captura correos y actualiza el Sheet, otro que toma el Sheet, llena los marcadores crudos y calculados en Slides, exporta PDF y lo manda por Gmail. Todavía sin IA — solo tipos 1 y 2. Al terminar tendrán un sistema funcional end-to-end."

**Pre-work / Tarea implícita:** crear cuenta gratuita de Make ([make.com](https://make.com/){:target="_blank"}) antes de la próxima clase. Sin cuenta, no se puede hacer el lab.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes llegaron a 18+ marcadores?
- ¿Hubo plantillas con diseños muy sobrios vs muy cargados? (guía para Clase 7 cuando personalicen)
- ¿Quién tuvo problemas con caracteres especiales en nombres? (seguimiento)
- ¿Ya crearon cuenta de Make? (mandar recordatorio por chat)
