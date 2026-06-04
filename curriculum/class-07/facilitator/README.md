# Guía del Facilitador - Sesión 07: Proyecto integrador

> Tiempo de lectura: 7 minutos | Prepárate antes de clase
>
> ⚠️ **Sesión con acompañamiento 1 a 1.** Prepárate para circular y dar soporte individual — no es una clase magistral.

---

## 🔑 Conceptos Clave

- **Estructura del proyecto**: problema → solución → arquitectura.
- **Diagramar**: dibujar el flujo (trigger → módulos → output) antes de construir.
- **Iteración**: construir v1, probar con datos reales, refinar.
- **Transferencia**: aplicar el método del caso de facturas a un caso propio.

---

## 🔗 Analogías Útiles

**Transferencia ⟷ cocinar un plato nuevo con técnicas que ya dominas:**
Si aprendiste a hacer risotto, las técnicas (tostar el arroz, añadir caldo, revolver) sirven para cualquier risotto. El método se queda; los ingredientes cambian. Aquí: la arquitectura se queda, el caso cambia.

**Diagramar ⟷ el plano antes de la obra:**
Nadie construye una casa sin plano. Una hoja con cajas y flechas (trigger, módulos, output) ahorra horas de retoque en Make.

---

## 📚 Contexto para Compartir

### Por qué adaptar > usar plantillas universales

Las "plantillas universales" suelen abandonarse en 1-2 meses; los sistemas que perduran son los **adaptados al caso específico**, porque el dueño los entiende y los mantiene. Por eso el curso enseña el método sobre un caso (facturas) y hoy cada quien lo lleva al suyo.

> **Para contar en clase:** "Un sistema que entiendes y mantienes vale más que uno perfecto que no tocaste."

### Diagramar primero ahorra tiempo

El error más común es saltar directo a Make. 10 minutos de diagrama en papel evitan una hora de módulos mal conectados.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "¿Qué proceso de tu trabajo automatizarías HOY si pudieras, y quién recibiría el resultado?"

**Respuesta esperada:** varía por estudiante — ese es su proyecto integrador.

**Script post-respuestas:**
```
Facilitador: "Esa idea es tu proyecto. Hoy la convertimos en flujo.
Antes de tocar Make, la vamos a diagramar."
```

### Demo Principal

**Qué mostrar:** diagramar un flujo en una hoja y luego armar la v1 partiendo de un escenario duplicado (Export/Import Blueprint).

**Script sugerido:**
```
Facilitador: "Primero el plano: trigger acá, IA en el medio, output allá."
[Dibuja cajas y flechas]
Facilitador: "Ahora duplico mi escenario de facturas y lo reapunto a este caso."
[Export/Import Blueprint → reconecta módulos]
```

**Plan B:** ten un video corto del proceso Export/Import y un diagrama de ejemplo.

### Transición al Mini-proyecto

**Momento crítico:** algunos no tienen datos reales y se paralizan.

**Script sugerido:**
```
Facilitador: "Si no tienen datos reales a mano, inventen simulados realistas.
El objetivo es VER el flujo funcionar, no tener datos perfectos."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Tu flujo en 3 frases"

Al inicio, cada quien escribe en el chat: problema / solución / resultado de su caso. Detecta de inmediato quién tiene el caso claro y quién necesita ayuda.

### Dinámica 2: "El 1 a 1 compartido"

Cuando resuelves el problema de alguien, pide proyectar su pantalla: "Creo que otros tienen lo mismo." Convierte un soporte individual en aprendizaje grupal.

---

## 💡 Ejemplos Listos para Usar

### Diagrama mínimo (para mostrar)

```
[Trigger: correo/archivo nuevo]
        ↓
[Gemini extrae datos → JSON]
        ↓
[Parse JSON → Sheet]
        ↓
[Plantilla → documento → destinatario]
```

### Diagnóstico rápido "no recibo datos"

```
□ ¿El escenario está activo (toggle On)?
□ ¿El trigger captura tu entrada? (probá con un caso real)
□ ¿Los módulos apuntan a TU Sheet/plantilla, no al de facturas?
□ El History muestra qué módulo falló y por qué.
```

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Salté a Make sin diagramar" | Se pierde en módulos | Pedir que dibuje el flujo en papel primero |
| "Duplicó pero no adaptó" | Mismo contenido de facturas | Revisar que el prompt y los campos sean de SU caso |
| "No tengo datos reales" | Parálisis de perfeccionismo | Usar simulados realistas; lo importante es validar |
| "No recibo datos" | Trigger o mapeo mal | Revisar toggle, filtro y a qué Sheet apunta |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Define su caso como problema → solución → arquitectura
- Diagrama antes de construir
- Su flujo apunta a SU caso, no a facturas disfrazado

### El estudiante NECESITA AYUDA cuando:
- Salta a Make sin plan
- Duplicó el flujo de facturas sin adaptarlo
- No sabe qué datos usar (parálisis)

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura | Cada quien escribió problema/solución/resultado | Ayudar a definir el caso a los que dudan |
| 30 | Diagrama listo | Tienen el flujo dibujado | Sentarse 2 min a dibujarlo juntos |
| 55 | v1 corriendo | El flujo corre con datos reales | Priorizar que funcione punta a punta aunque básico |
| 60 | Cierre | Cada quien sabe qué mostrará en Demo Day | — |

---

## 🧑‍🏫 Tips de Facilitación

### Sesión con acompañamiento 1 a 1:
- Circula constantemente; no te quedes frente a tu pantalla.
- Lleva un "score" mental de quién diagramó, quién ya tiene v1.
- Prioriza 1:1 con casos muy distintos al de facturas.

- **Si el grupo está callado:** normal en sesión de construcción — es concentración.
- **Si alguien va muy avanzado:** conviértelo en mentor de pares.
- **Si la mayoría se atrasa:** prioriza que la v1 corra, aunque falten refinamientos.
- **Preguntas fuera de alcance:** "Guárdala para tu plan de próximos pasos en Demo Day."

---

## ❓ Preguntas Frecuentes

### P: ¿Tengo que construir desde cero?
**R:** No. Lo más rápido es duplicar tu escenario de facturas (Export/Import Blueprint) y adaptarlo a tu caso.

### P: ¿Qué pasa si mi reporte no es semanal?
**R:** Ajusta el trigger a tu frecuencia real (diario, quincenal, mensual) o usa Watch si reaccionas a eventos.

### P: ¿Y si mi caso no encaja en `scenarios.md`?
**R:** Usa la sección "Plantilla para tu caso" del apéndice — los bloques son genéricos para adaptar.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 2-6 | El método completo | Hoy se aplica a un caso propio |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "La próxima sesión es Demo Day: 5 minutos por persona con tu sistema funcionando en vivo. Llega con tu flujo pulido y datos de prueba listos para dispararlo frente al grupo."

**Pre-work / Tarea implícita:** practicar la demo y cronometrar los 5 minutos. Dos ensayos reducen los nervios mucho.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos terminaron con una v1 propia corriendo?
- ¿Quiénes tienen casos muy distintos y necesitan apoyo antes de Demo Day?
- ¿Quiénes siguen sin datos reales? (sugerir alternativas antes de la Sesión 8)
