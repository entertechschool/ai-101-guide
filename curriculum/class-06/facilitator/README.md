# Guía del Facilitador - Sesión 06: Flujo end-to-end robusto

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Watch vs Schedule**: trigger por evento (tiempo real) vs programado (a hora fija).
- **Filtro**: condición que deja pasar solo lo que cumple un criterio.
- **Router**: bifurcación que envía cada caso por una ruta distinta.
- **Error handler**: módulo que reacciona si algo falla (Resume, Rollback, Ignore).
- **Log**: registro de cada ejecución para depurar (History de Make).

---

## 🔗 Analogías Útiles

**Watch vs Schedule ⟷ timbre vs alarma:**
El timbre suena cuando alguien llega (evento). La alarma suena a la hora fijada aunque no haya nadie. Watch para reaccionar en vivo; Schedule para tareas periódicas.

**Filtro / Router ⟷ portero y señalizador:**
El filtro es el portero que deja entrar solo a quien cumple (PDF, monto > 0). El router es el señalizador que manda a cada uno por su pasillo (facturas grandes por aquí, normales por allá).

**Error handler ⟷ extintor:**
No lo usas casi nunca, pero el día que hay fuego, es la diferencia entre un susto y un desastre. Un flujo sin handler falla en silencio.

---

## 📚 Contexto para Compartir

### Por qué "robusto" no es opcional

Un flujo demo funciona con datos perfectos. El mundo real trae archivos corruptos, campos vacíos, feriados, formatos raros. Los filtros, routers y handlers son lo que separa "funcionó una semana" de "funciona dos años".

> **Para contar en clase:** "El día que tu flujo se rompa —y se va a romper— la pregunta es: ¿te enteras vos primero, o el cliente?"

### Depurar es una habilidad, no magia

El History de Make muestra cada corrida módulo por módulo, con entrada y salida. Saber leerlo vuelve al estudiante autónomo: puede arreglar su propio flujo sin depender de nadie.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "Si tu flujo se cayera un viernes a las 4pm, ¿cómo te enterarías?"

**Respuesta esperada:** Hoy, probablemente no me entero hasta que alguien reclama.

**Script post-respuestas:**
```
Facilitador: "Esa es la diferencia entre un flujo de juguete y uno de producción.
Hoy le ponemos sensores: filtros para no procesar basura, y alertas para enterarte antes que nadie."
```

### Demo Principal

**Qué mostrar:** subir un archivo que NO es factura (se salta por el filtro) y una factura grande (dispara la alerta del router), en vivo.

**Script sugerido:**
```
Facilitador: "Subo un PDF que no es factura... miren, el filtro lo salta, no gasta IA."
[Sube una factura grande]
Facilitador: "Esta es grande. El router la manda por la ruta de alerta y me llega un correo."
```

**Plan B (si falla en vivo):** ten el escenario con filtro/router ya armado y muestra el History de corridas pasadas.

### Transición al Mini-proyecto

**Momento crítico:** integrar todo en un escenario puede abrumar. Que partan de los escenarios ya armados y los conecten, no que empiecen de cero.

**Script sugerido:**
```
Facilitador: "No armen un escenario nuevo desde cero. Tomen lo que ya tienen y conéctenlo.
Luego le agregamos el portero (filtro), el señalizador (router) y el extintor (handler)."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Watch o Schedule"

Lanza casos y el grupo responde:

```
"Procesar una factura apenas llega" → Watch
"Enviar el reporte cada lunes 8am" → Schedule
"Avisar cuando un cliente responde" → Watch
"Resumen mensual el día 1" → Schedule
```

### Dinámica 2: "¿Dónde se rompe?"

Muestra un flujo y pregunta dónde podría fallar y qué handler pondrían. Entrena el pensamiento de robustez.

---

## 💡 Ejemplos Listos para Usar

### Filtro PDF + monto

```
Condición 1:  File extension  equals         "pdf"
    AND
Condición 2:  Monto detectado greater than   0
```

### Error handler con alerta

```
Click derecho en el módulo frágil → Add error handler → Resume
   ↓
[Gmail Send an Email]
   Subject: ❌ Error en el flujo de facturas — {{formatDate(now; "YYYY-MM-DD HH:mm")}}
   Body: Falló el módulo [nombre]. Revisar Make History.
```

**Tip:** "Resume" continúa con el siguiente item; "Rollback" cancela toda la corrida.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "El filtro no deja pasar nada" | Condición demasiado estricta o campo mal referenciado | Revisar el campo y el valor exacto del filtro |
| "El router manda todo por una ruta" | Falta condición en la otra ruta | Definir condición explícita en cada ruta |
| "El error handler no se activa" | Está en Rollback por defecto | Cambiar a Resume |
| "No sé por qué falló" | No revisó el History | Abrir History → módulo rojo → ver entrada/salida |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Elige Watch o Schedule según el caso sin dudar
- Explica qué hace el filtro y qué hace el router con un ejemplo propio
- Sabe que el error handler "Resume" deja seguir el flujo

### El estudiante NECESITA AYUDA cuando:
- Confunde filtro con router
- No revisa el History para depurar
- Deja el flujo sin ningún manejo de error

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Distinguen Watch/Schedule, filtro/router | Repetir la dinámica "Watch o Schedule" |
| 55 | Mini-proyecto listo | Flujo con filtro + router + handler, probado con un caso límite | Priorizar filtro + handler; el router queda opcional |
| 60 | Cierre | Cada quien muestra una corrida en el History | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo se atrasa:** prioriza filtro + error handler; el router queda como logro adicional.
- **Si alguien termina antes:** propón el Logro 🟡 (carpeta Backups) o 🔴 (dashboard de Logs).
- **Si nadie sabe depurar:** dedica 3 min a abrir el History juntos y leer una corrida.
- **Preguntas sobre el caso propio:** "Eso es justo la próxima sesión: aplicas todo esto a TU caso real."

---

## ❓ Preguntas Frecuentes

### P: ¿Cuántos error handlers necesito?
**R:** Uno por módulo frágil. Los más frágiles suelen ser la llamada a la IA y la escritura en Sheets.

### P: ¿El filtro consume operaciones?
**R:** El filtro en sí no; lo que ahorra es no ejecutar los módulos siguientes (incluida la IA) sobre lo que no corresponde.

### P: ¿Watch o Schedule para mi caso?
**R:** Si necesitas reaccionar al instante, Watch. Si es un resumen periódico, Schedule. Muchos sistemas usan ambos.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 02-05 | Piezas del sistema | Hoy se integran en un solo flujo |
| 05 | Plantilla / documento | Es la salida final del flujo completo |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "Ya tienes un sistema completo y robusto sobre el caso de facturas. La próxima sesión das el salto: aplicas todo esto a TU caso real. Llega con un proceso de tu trabajo en mente y, si puedes, datos reales."

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos lograron el flujo con filtro + router + handler?
- ¿Quiénes saben leer el History para depurar solos?
- ¿Quiénes ya tienen claro su caso propio para la Sesión 7? (mandar recordatorio de traer datos reales)
