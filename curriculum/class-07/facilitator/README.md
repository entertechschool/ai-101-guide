# Guía del Facilitador - Clase 07: Tu proyecto propio

> Tiempo de lectura: 10 minutos | Prepárate antes de clase
>
> ⚠️ **Clase con acompañamiento 1 a 1.** Preparate para circular y dar soporte individual — no es una clase magistral.

---

## 🔑 Conceptos Clave

- **Transferencia**: aplicar el patrón aprendido (caso Roberto) a un contexto nuevo (caso real del estudiante).
- **Clonación de escenario**: duplicar un flujo completo en Make vía Export/Import Blueprint.
- **Personalización**: adaptar datos, marca, métricas y prompts al caso específico.
- **Debug en Make**: aislar problemas con "Run this module only" sobre módulos frágiles.

---

## 🔗 Analogías Útiles

**Transferencia <> aprender a cocinar un plato nuevo con técnicas que ya dominás:**
Si aprendiste a hacer risotto, sabés que el arroz se tuesta, se añade caldo caliente gradualmente, se revuelve. Esas técnicas sirven para un risotto de champiñones, mariscos o trufa. El patrón se queda; los ingredientes cambian. En el sistema es igual: la arquitectura se queda, el caso cambia.

**Clonar escenario <> moldear galletas con un cortador:**
El cortador (blueprint) es el mismo. El ingrediente (masa = tu caso) cambia. Lo que sale tiene la forma del cortador pero el sabor de tu ingrediente. Duplicar un escenario preserva la forma; los datos son tu sabor.

---

## 📚 Contexto Histórico / Contexto Actual

### El mito del "sistema universal" vs la realidad de la personalización

En 2020-2022, muchas herramientas no-code prometían "plantillas universales que sirven para cualquier negocio". La realidad mostró que esos sistemas terminaban usándose por 1-2 meses y se abandonaban. Los que perduran son los **adaptados al caso específico**. Hoy la mejor práctica es: aprender el patrón → adaptarlo. Exactamente lo que hace esta clase.

> **Para contar en clase:** "Las plantillas 'universales' fallan porque cada trabajo tiene matices. Un sistema adaptado a TU caso sobrevive porque vos lo entendés y lo podés mantener."

**Fuentes:** [Make: Blueprints](https://www.make.com/en/help/scenarios/exporting-importing-a-blueprint){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "Si tuvieras que escribir el SystemPrompt de TU caso en este momento, ¿qué palabra clave incluirías que NO está en el de Roberto?"

**Respuesta esperada:** varía por estudiante — tu industria, tu métrica clave, tu vocabulario.

**Script post-respuestas:**
```
Facilitador: "Exacto — esas palabras son el 'cerebro' que le vamos a cambiar al sistema hoy.
La arquitectura se queda igual, pero todo lo que diga 'ventas', 'vendedor', 'monto'
va a pasar a decir algo que tenga sentido en TU trabajo."
```

### Demo Principal

**Qué mostrar:** Export Blueprint + Import Blueprint de un escenario, y cómo reconectar los módulos al Sheet nuevo.

**Script sugerido:**
```
Facilitador: "Voy a duplicar mi Escenario 1 en 30 segundos."
[Menú (...) → Export Blueprint → download]
[+ Create scenario → Import Blueprint → upload]
Facilitador: "Tengo el mismo escenario. PERO apunta al Sheet viejo."
[Click en Search Rows → elegir Sheet v2]
[Click en Add a row → elegir Sheet v2 → pestaña CampanasSemanaActual]
Facilitador: "Ahora es el cerebro de MI caso. Esto es lo que van a hacer hoy."
```

**Plan B:** tener un video pregrabado de 2 min del proceso Export/Import.

### Transición al Lab

**Momento crítico:** algunos estudiantes no tienen datos reales y se paralizan.

**Script sugerido:**
```
Facilitador: "Si no tienen datos reales de su trabajo en este momento, inventen simulados
REALISTAS. Nombres de clientes reales pueden ser reemplazados por 'Cliente A', 'Cliente B',
pero las métricas y fechas deben ser plausibles. El objetivo es VALIDAR el sistema,
no tener datos perfectos."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Tu prompt en voz alta"

Contexto: durante la Actividad 2, cuando algún estudiante está atascado con el SystemPrompt.

Pedís que 2-3 estudiantes lean sus SystemPrompts adaptados:

```
Facilitador: "Leé los 3 primeros bloques de tu prompt: Persona, Contexto, Reglas."
[Estudiante lee]
Facilitador: "¿Qué del caso Roberto sigue ahí sin adaptar?"
(Típicamente: una referencia a "ventas" o "vendedores" que quedó olvidada)
```

### Dinámica 2: "El 1 a 1 compartido"

Contexto: cuando resolvés un problema de un estudiante en vivo.

Pedís permiso al estudiante para proyectar su pantalla y resolver juntos:

```
Facilitador: "María, ¿puedo proyectar tu pantalla? Creo que otros tienen el mismo problema."
[Proyecta]
Facilitador: "Miren — el Search Rows apunta al Sheet modelo, no al v2.
Esa es la reconexión que mencionamos en la demo. Quien tenga el mismo síntoma, esta es la fix."
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Troubleshooting rápido de "Replace Text no reemplaza"

**Cuándo usarlo:** problema frecuente en Actividad 2/3.

```
1. Abrí la plantilla Slides v2 en otra pestaña
2. Buscá el marcador exacto (Ctrl+F "{{ventas_total}}")
3. Si cambiaste a "{{alcance_total}}" en Slides pero Make todavía dice "{{ventas_total}}",
   reemplazá en el Replace Text del Make
4. Regla: el texto debe ser IDÉNTICO en ambos lados, letra por letra
```

### Ejemplo 2: Diagnóstico "mi Sheet v2 no recibe filas"

**Cuándo usarlo:** Actividad 3, al probar correos reales.

```
Checklist:
□ ¿El Escenario 1 v2 está ACTIVO (toggle On)?
□ ¿El filtro de asunto captura tu correo? (enviá uno con exacto el asunto del filtro)
□ ¿El módulo Add a row apunta al Sheet v2 y a la pestaña correcta?
□ ¿Las columnas del mapping coinciden con las de la pestaña v2?

Si falla: Run History del escenario muestra qué módulo falló y por qué.
```

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Duplicación fallida en Make" | Blueprint con referencias a recursos privados | Export manual con "Include connections" desmarcado |
| "Gemini sigue dando insights de Roberto" | SystemPrompt no actualizado en el HTTP v2 | Abrir módulo HTTP → editar el body JSON del prompt |
| "No tengo logo/paleta" | Estudiante no preparó elementos de marca | Usar texto simple con la tipografía del Sheet; Canva tiene paletas gratuitas rápidas |
| "Datos simulados no me convencen" | Estudiante quiere datos reales pero no tiene | Priorizar: ver el sistema funcionar > perfección; usará datos reales en su trabajo después |
| "Escenario v2 tiene el mismo nombre que el modelo" | Confusión al activar | Renombrar con "v2" o el nombre de su caso |
| "Rangos nombrados no funcionan" | Renombró la pestaña pero el rango apunta al nombre viejo | Datos → Rangos con nombre → editar o recrear |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Su Sheet v2 tiene pestañas y columnas de SU caso (no Roberto disfrazado)
- Su SystemPrompt menciona su industria específica, no "ventas"
- Puede explicar por qué la arquitectura se queda y el contenido cambia

### El estudiante NECESITA AYUDA cuando:
- Duplicó archivos pero no los adaptó (mismo contenido de Roberto)
- No sabe qué datos reales usar (parálisis de perfeccionismo)
- Su PDF v2 sale igual al PDF del caso Roberto

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura | Plan de personalización revisado en voz alta | Ajustar puntos vagos antes de arrancar |
| 15 | Demo Export/Import terminada | Quiz de COMPROBACIÓN correcto | Repetir demo si hay confusión |
| 65 | Actividad 1 | Sheet v2 con pestañas y datos reales | 1 a 1 con rezagados 5 min |
| 120 | Actividad 2 | Slides v2 con marca + 2 escenarios v2 apuntando a v2 | Checklist: Search Rows, Replace Text, Add a row |
| 140 | Actividad 3 | PDF del reporte v2 con datos reales | Si falla, debug "Run this module only" |
| 150 | Cierre | Sistema funcionando end-to-end para SU caso | — |

---

## 🧑‍🏫 Tips de Facilitación

### Clase con acompañamiento 1 a 1:
- Circular constantemente, no quedarse frente a la pantalla
- Llevar un "score" mental: quién terminó Actividad 1, quién está atascado en Actividad 2
- Priorizar 1:1 con quienes tienen casos muy distintos a Roberto

### Si el grupo está callado:
- Típico en clase de construcción — no hay que forzar discusión
- Señal de concentración, no de confusión

### Si alguien domina la conversación:
- Probablemente está avanzado — convertilo en mentor de pares
- "¿Podrías ayudar a Juan 5 min? Él tiene un caso parecido al tuyo."

### Si la mayoría termina antes:
- Logro 🟡 (versión móvil) o 🔴 (indicador de salud).
- Tiempo extra para pulir diseño visual.

### Si la mayoría se atrasa:
- Priorizar Actividad 1 (Sheet) y Actividad 3 (validación end-to-end).
- Actividad 2 puede completarse post-clase (menos crítico para Demo Day).

### Si hay preguntas fuera de alcance:
> "Guardá esa — es perfecta para explorar en tu plan 30 días de Clase 8."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logros 🟡 y 🔴 rápido → mentor de pares.
- Proponer que agreguen un segundo formulario de entrada (ej: WhatsApp Business, Google Forms).

### Para estudiantes con dificultades:
- Ofrecer Blueprint pre-hecho del escenario ajustado a su caso (si conocés la industria).
- Sentarse 10-15 min con ellos en la Actividad 2 para reconfigurar escenarios juntos.
- Alternativa: que usen el caso Roberto literal y lo presenten como "ejemplo del curso" en Demo Day (menos ideal pero funcional).

---

## ❓ Preguntas Frecuentes

### P: ¿Tengo que adaptar TODOS los marcadores, o puedo dejar algunos iguales?
**R:** Los crudos y calculados SÍ adaptar (vienen del Sheet, así que sus nombres deberían reflejar tus columnas). Los tipo IA pueden quedar iguales (`hallazgo_1`, `riesgo_1`) — el contenido se adapta vía SystemPrompt.

### P: ¿Qué pasa si mi reporte no es semanal?
**R:** Cambiá el trigger del Escenario 2 a tu frecuencia real: diario, quincenal, mensual. Make soporta cualquier intervalo estándar.

### P: ¿Puedo tener más de una plantilla de Slides?
**R:** Sí, pero duplicá el Escenario 2 para cada una. Cada escenario apunta a una plantilla específica.

### P: ¿Y si mi caso no encaja en ninguno del `scenarios.md`?
**R:** Usá la sección "Plantilla para TU caso" al final. Los bloques son genéricos para adaptar.

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| Todo el M1 | Piezas modelo | Hoy se copian y adaptan |
| 05 | Gemini API | Los prompts se re-personalizan |
| 06 | Prompts optimizados + personalización | El roadmap se ejecuta |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase es Demo Day. 5 minutos por estudiante con demo en vivo de TU sistema funcionando. Calculás tu ROI en horas ahorradas × tarifa y armás un plan 30 días con 3 próximos agentes. Lleguen con su sistema pulido y 3 correos de prueba reales para disparar en vivo."

**Pre-work / Tarea implícita:** practicar la demo frente al espejo/cámara. Cronometrá los 5 minutos. Los nervios se reducen 70% con 2 ensayos.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes terminaron con sistema propio funcionando end-to-end?
- ¿Quiénes tuvieron casos muy distintos al modelo? (seguimiento antes de Demo Day)
- ¿Hay estudiantes sin datos reales? (sugerir alternativas creativas antes de C8)
- ¿Quiénes necesitan mentoría extra antes de presentar? (oferta 1:1 opcional)
