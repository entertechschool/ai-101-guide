# Guía del Facilitador - Sesión 05: Plantillas con placeholders

> Tiempo de lectura: 7 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Plantilla**: esqueleto con formato fijo y datos variables.
- **Placeholder**: marcador `{{variable}}` que Make reemplaza por un dato real.
- **Mapeo**: asignar qué variable del flujo va en cada placeholder.
- **Create from Template**: módulo de Make que genera un Doc/Slide desde la plantilla.
- **formatDate / formatNumber**: funciones para dar formato a fechas y números.

---

## 🔗 Analogías Útiles

**Plantilla con placeholders ⟷ contrato con espacios en blanco:**
Un contrato tipo tiene huecos donde se escribe el nombre, la fecha, el monto. El cuerpo no cambia; solo los huecos. Make es la mano que llena los huecos con los datos del Sheet.

**Mapeo ⟷ etiquetar maletas:**
Si las etiquetas no coinciden con el destino, la maleta llega al lugar equivocado. Si el placeholder `{{total}}` no coincide con el mapeo, el dato no llega y el marcador queda literal.

**Formato de datos ⟷ vestir el dato:**
`1500` es correcto pero se ve pobre. `S/ 1,500.00` es el mismo dato "vestido" para presentar. formatNumber/formatDate hacen ese vestuario.

---

## 📚 Contexto para Compartir

### El patrón plantilla + datos es universal

Looker Studio, mailings, generadores de PDF, facturadores: todos usan el mismo patrón hace años. Make + Google Slides lo trae a no-code gratis. Lo que el estudiante aprende hoy aplica a cualquier documento repetitivo, no solo reportes de facturas.

> **Para contar en clase:** "Lo que las agencias hacen con software de cientos de dólares al mes, ustedes lo hacen con Slides + Make gratis."

### Por qué el nombre exacto importa tanto

Replace Text / Create from Template buscan coincidencia literal. `{{Total}}` ≠ `{{total}}`. Un espacio o una mayúscula de más y el marcador queda sin reemplazar. Conviene sembrar disciplina de nombres desde hoy.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "¿Cuántos reportes haces al mes que son básicamente el mismo formato con datos distintos?"

**Respuesta esperada:** varía; casi todos tienen al menos uno (reporte mensual, ficha, resumen).

**Script post-respuestas:**
```
Facilitador: "Ese reporte que repiten cada mes es justo lo que hoy convertimos en plantilla.
Lo diseñan una vez y se llena solo para siempre."
```

### Demo Principal

**Qué mostrar:** una plantilla de Slides con placeholders → correr el escenario → Slide generado con datos reales, en vivo.

**Script sugerido:**
```
Facilitador: "Esta plantilla tiene {{total}}, {{top_proveedor}}, {{mes}}..."
[Corre el escenario]
Facilitador: "Miren: Make leyó el Sheet, calculó el total y generó el reporte con formato. Cero diseño manual."
```

**Plan B (si Make falla):** ten una plantilla y un Slide ya generado para mostrar el antes/después.

### Transición al Mini-proyecto

**Momento crítico:** los nombres de placeholders. Insiste en coincidencia exacta.

**Script sugerido:**
```
Facilitador: "Regla de oro: el nombre del placeholder en la plantilla y en el mapeo deben ser idénticos.
Copien y peguen, no los reescriban a mano."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "¿Se reemplaza o no?"

Muestra pares y el grupo dice si el placeholder se reemplazará:

```
Plantilla {{total}}  ·  Mapeo total       → sí
Plantilla {{Total}}  ·  Mapeo total       → no (mayúscula)
Plantilla {{total }} ·  Mapeo total       → no (espacio)
Plantilla {{top_proveedor}} · Mapeo top_proveedor → sí
```

### Dinámica 2: "Viste el dato"

Lanza datos crudos y el grupo dice cómo deberían verse formateados:

```
1500        → S/ 1,500.00
2026-06-01  → 1 de junio de 2026
0.12        → 12%
```

---

## 💡 Ejemplos Listos para Usar

### Funciones de formato en Make

```
formatNumber(monto; 2; "."; ",")        → 1,500.00
formatDate(now; "D [de] MMMM [de] YYYY") → 1 de junio de 2026
formatDate(now; "MMMM")                  → junio
```

**Tip:** Make usa el estándar de formatos de fecha tipo moment.js.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "El marcador queda literal `{{total}}`" | Nombre no coincide o no se mapeó | Copiar/pegar el nombre exacto de la plantilla al mapeo |
| "El monto sale sin formato (1500)" | No aplicó formatNumber | Envolver con `formatNumber(...)` antes de inyectar |
| "La fecha sale en inglés" | Locale por defecto | Especificar el formato y, si aplica, idioma |
| "No encuentra mi plantilla" | Plantilla en carpeta no conectada | Verificar que la cuenta de Make tiene acceso a esa carpeta |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Nombra placeholders consistentes y los mapea sin error
- Aplica formato a montos y fechas sin que se lo recuerdes
- Distingue qué es fijo (plantilla) y qué es variable (placeholder)

### El estudiante NECESITA AYUDA cuando:
- Reescribe los nombres a mano y no coinciden
- Inyecta números crudos sin formato
- Confunde la plantilla con el documento generado

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Entienden placeholder + mapeo + formato | Repetir la dinámica "¿Se reemplaza o no?" |
| 55 | Mini-proyecto listo | Slide generado con datos reales, sin marcadores literales | Reducir a 3 placeholders (total, mes, proveedor) |
| 60 | Cierre | Cada quien muestra su Slide generado | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo se atrasa:** que empiecen con 3 placeholders y agreguen el resto después.
- **Si alguien termina antes:** propón el Logro 🟢 (versión en Docs) o 🔴 (enviar por correo).
- **Si quedan marcadores literales:** casi siempre es un nombre que no coincide — revisar copia exacta.
- **Preguntas sobre automatizar la entrega:** "Eso lo cerramos la próxima sesión, con el flujo completo de inicio a fin."

---

## ❓ Preguntas Frecuentes

### P: ¿Plantillas en Slides o en Docs?
**R:** Ambas funcionan con el mismo patrón. Slides para reportes visuales; Docs para cartas o fichas narrativas.

### P: ¿Puedo reemplazar imágenes también?
**R:** Sí, con Replace Image (por ejemplo, el logo). Hoy nos enfocamos en texto.

### P: ¿Y si tengo muchos datos (una tabla)?
**R:** Para listas/tablas se usan técnicas más avanzadas; para el reporte mensual, los agregados (total, top, conteo) alcanzan.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 04 | Datos estructurados en el Sheet | Son la fuente que llena la plantilla |
| 01 | Output con formato | Aquí el "formato" es el documento final |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "Ya tienes datos, IA y documentos. La próxima sesión unimos todo en un solo flujo robusto de inicio a fin —Drive → IA → Sheets → Docs → Email— con filtros, routers y manejo de errores para que aguante el mundo real."

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos generaron un Slide con todos los placeholders reemplazados?
- ¿Los problemas fueron de nombres o de formato? (patrón a reforzar)
- ¿Quiénes quedaron con marcadores literales? (seguimiento antes de la Sesión 6)
