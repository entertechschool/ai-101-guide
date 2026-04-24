# Guía del Facilitador - Clase 04: Make básico (sin IA)

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Escenario**: el flujo completo en Make (equivalente a "Zap").
- **Módulo**: cada paso del escenario (leer Gmail, escribir en Sheet, etc.).
- **Operación**: cada vez que un módulo ejecuta. Cuenta para el límite de 1,000/mes.
- **Conexión**: autenticación entre Make y tus apps (Gmail, Sheets).
- **Instant Trigger**: activación en 2-5 seg vía webhook/push; efecto "en vivo".
- **Scheduled Trigger**: revisión cada X tiempo; mejor para reportes periódicos.
- **Replace Text**: operación de Slides que reemplaza `{{marcador}}` por un valor.

---

## 🔗 Analogías Útiles

**Escenario <> receta de cocina:**
Cada módulo es un paso de la receta ("leer Gmail", "escribir en Sheet"). El orden importa — no podés "exportar PDF" antes de "reemplazar marcadores". Make es el cocinero que sigue la receta cada vez que se activa el trigger.

**Instant vs Scheduled <> campanilla vs reloj:**
Instant = campanilla en el mostrador (suena cuando alguien llega). Scheduled = alarma del reloj (suena a la hora programada aunque no haya nadie). La campanilla es mejor para atención al cliente; la alarma es mejor para tareas periódicas.

**Operaciones <> stamps en una tarjeta de café:**
Tenés 1,000 stamps al mes. Cada "taza" (ejecución de módulo) consume un stamp. Flujos frecuentes consumen rápido; flujos semanales duran meses. Monitorear stamps = monitorear consumo de Make.

---

## 📚 Contexto Histórico / Contexto Actual

### Make (antes Integromat): de nicho técnico a estándar no-code

Integromat nació en 2016 en República Checa como competencia directa de Zapier, con diferenciador clave: interfaz visual con nodos conectados (como Figma para automatización). En 2022 cambió el nombre a Make después de ser adquirida por Celonis. Hoy (2025) tiene 250K+ usuarios activos, 1,500+ integraciones, y un plan gratuito muy generoso (1,000 ops/mes) que lo volvió favorito de no-code creators.

> **Para contar en clase:** "Lo que las empresas pagan $500-$5,000/mes con Zapier Enterprise, ustedes lo hacen con 1,000 ops gratis mensuales. Para un reporte semanal (~10 ops), eso son 100+ reportes al mes. Alcanza."

### Instant Trigger: por qué cambió el juego

Antes de los Instant Triggers (2020-2021), todo flujo se activaba cada 5-15 min. Eso no es "tiempo real" — es "casi tiempo real". Cuando Make implementó webhooks directos de Gmail y Google Forms, el efecto visible fue que la automatización pasó de "útil" a "mágica" para la audiencia no técnica.

> **Para contar en clase:** "La diferencia entre reaccionar en 15 minutos y reaccionar en 5 segundos no es técnica — es percepción. Lo que percibe tu jefe o cliente como 'magia' es lo que vende automatización."

**Fuentes:** [Make: About](https://www.make.com/en/about){:target="_blank"}, [Make: Pricing](https://www.make.com/en/pricing){:target="_blank"}

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Quiz Pre-Lab)

**Pregunta:** "Si pudieras automatizar solo UNA tarea de tu trabajo esta semana, ¿cuál sería y por qué?"

**Respuesta esperada:** varía por estudiante. Tu trabajo es anotar mentalmente los casos — en Clase 7 cada uno aplicará el sistema a SU caso, y las respuestas de hoy son material valioso para esa transferencia.

**Script post-respuestas:**
```
Facilitador: "Guardá esa respuesta. En 3 clases vas a adaptar el sistema
que construimos hoy a exactamente ESE caso que acabás de mencionar.
Hoy construimos el modelo; en Clase 7 vos lo hacés tuyo."
```

### Demo Principal

**Qué mostrar:** el Instant Trigger funcionando en vivo. Enviás un correo a tu propia cuenta con el asunto filtro, y en menos de 10 segundos el Sheet se actualiza en pantalla compartida.

**Script sugerido:**
```
Facilitador: "Miren mi Sheet — tiene X filas ahora."
[Envía correo desde otra cuenta]
Facilitador: "Acabo de enviar un correo. Esperen..."
[5-8 segundos después, aparece la fila nueva]
Facilitador: "Ese es el efecto WOW. Esto es lo que vamos a construir hoy."
```

**Plan B (si Instant no dispara):** tener un video de 20 segundos pregrabado del efecto.

### Transición al Lab

**Momento crítico:** el setup de Make (cuenta + conexiones con Gmail y Sheets) puede tomar 10 min por estudiante. Es crítico que la cuenta esté creada antes de la clase.

**Script sugerido:**
```
Facilitador: "Levanten la mano si YA tienen cuenta de Make creada."
[Contar manos]
Facilitador: "Los que no, tómense 2 minutos ahora.
Los demás, conecten Gmail y Google Sheets (Settings → Connections)."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "La cadena de módulos"

Contexto: durante la teoría, para consolidar el concepto de escenario.

Pedís al grupo armar el escenario 2 en voz alta, en orden:

```
Facilitador: "¿Cuál es el trigger del escenario 2? (Manual/Run once por ahora)
[Toma respuesta]
Facilitador: "¿Qué sigue? Necesitamos los datos del Sheet..."
[Respuesta: Search Rows]
Facilitador: "¿Y después?"
[Continúan hasta: Create from Template → Replace Text (varios) → Export PDF → Send Email]
```

### Dinámica 2: "Cazadores de operaciones"

Contexto: en medio del lab, si surge tema de consumo de Make.

Cada estudiante cuenta cuántas operaciones consume su escenario 2 por reporte generado:

```
Facilitador: "Cuenten los módulos de su escenario 2.
Cada Replace Text = 1 op. Cada módulo = 1 op.
¿Cuántas ops por reporte?"
[Respuestas: 10-15 típicamente]
Facilitador: "Con 1,000 ops/mes, ¿cuántos reportes pueden correr?"
[80-100 reportes mensuales]
Facilitador: "Más que suficiente. Ahora agreguen 18 marcadores tipo IA en Clase 5..."
[Nuevo cálculo: 28-33 ops → ~30 reportes mensuales]
```

---

## 💡 Ejemplos Listos para Usar

### Ejemplo 1: Formato de fecha en Make

**Cuándo usarlo:** cuando un estudiante pregunta cómo formatear fechas para el marcador `{{semana}}`.

```
formatDate(now; "DD/MM/YYYY")        → 19/04/2026
formatDate(now; "dddd, DD MMMM")     → lunes, 19 abril
formatDate(parseDate(fecha; "..."); "YYYY-MM-DD")  → conversión entre formatos
```

**Tip:** Make usa el estándar [moment.js](https://momentjs.com/docs/#/displaying/format/) para formatos.

### Ejemplo 2: Cálculo de variación porcentual

**Cuándo usarlo:** marcador `{{variacion_pct}}`.

```
Módulo Math → Set multiple variables
  ventas_actual = {{sheet_module.ventas_total}}
  ventas_anterior = {{historico_module.ventas_semana_pasada}}
  variacion = (ventas_actual - ventas_anterior) / ventas_anterior * 100

En Replace Text:
  {{round(variacion; 1)}}%
```

**Tip:** siempre redondear con `round(valor; decimales)` antes de pasarlo a Replace Text.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No me conecta Gmail" | 2FA activado sin App Password | Generar [App Password](https://myaccount.google.com/apppasswords){:target="_blank"} o usar cuenta personal |
| "Instant Trigger no dispara" | Falta activar el webhook / no subscribió | Click "Run once" en el trigger primero para activarlo |
| "Replace Text no reemplaza" | Texto exacto no coincide (espacio o mayúscula) | Copiar/pegar el marcador desde la plantilla de Slides |
| "Export PDF da error" | Plantilla sin permiso de edición de Make | Verificar que la cuenta conectada tiene edit access |
| "Consumo operaciones muy alto" | Escenario no tiene filtro → captura todo | Agregar filtro específico en el trigger |
| "Correo llega sin adjunto" | Módulo Send Email no recibió output del Export PDF | Verificar mapping del campo Attachments |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Distingue trigger de módulo regular sin dudar
- Predice cuántas operaciones consume su escenario
- Sabe por qué eligió Instant vs Scheduled para cada caso

### El estudiante NECESITA AYUDA cuando:
- Corre Run once cada vez que hace un cambio (en vez de activar el trigger)
- Se confunde entre "Sheet Search" y "Sheet Add" (lectura vs escritura)
- No usa módulos Date/Math para calculados (pone valores hardcoded)

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura + demo del Instant Trigger | Todos vieron el efecto WOW | Mostrar video pregrabado si Instant falla |
| 30 | Teoría terminada | Quiz Pre-Lab respondido | Tomar 1-2 respuestas y seguir |
| 70 | Actividad 1 | Instant Trigger activo + 3 filas en Sheet | Revisar filtro y reconexión Gmail |
| 105 | Actividad 2 | Escenario 2 con Run once exitoso + 5 marcadores | Si no llegan, ofrecer ayuda 1 a 1 |
| 130 | Actividad 3 | Correo con PDF en bandeja | Si falla, revisar módulo Send Email |
| 150 | Cierre | Compromiso de completar desafío + entrega | — |

---

## 🧑‍🏫 Tips de Facilitación

### Si el grupo está callado:
- Pedir que 2 estudiantes compartan pantalla simultáneamente durante la Actividad 1.
- Preguntar por el caso específico de alguien ("¿A quién le llegaron sus filas?").

### Si alguien domina la conversación:
- Pedirle que comparta screenshot de su flujo completo como referencia para el grupo.

### Si la mayoría termina antes:
- Logro 🟢 (pestaña Logs) o 🔴 (preparar scheduled trigger).

### Si la mayoría se atrasa:
- Recortar a Escenario 1 completo + Escenario 2 hasta Replace Text (sin PDF ni Gmail). El resto se completa post-clase.
- Posponer Actividad 3 (Export + Send Email) al desafío post-clase.

### Si hay preguntas fuera de alcance:
> "Excelente pregunta. Gemini API en Make lo vemos la próxima clase."

---

## 🔀 Diferenciación

### Para estudiantes avanzados:
- Logro 🔴 (preparar scheduled trigger) + ayudar a compañeros rezagados.
- Pedirles que calculen operaciones totales que consumirá el sistema en Clase 5 cuando agreguemos IA.

### Para estudiantes con dificultades:
- Usar el "Blueprint" del escenario de Roberto como template (importar → ajustar).
- Sentarse 5-10 min durante Actividad 2 para configurar el primer Replace Text juntos; los siguientes los hacen solos.

---

## ❓ Preguntas Frecuentes

### P: ¿Qué pasa si excedo las 1,000 operaciones del plan gratuito?
**R:** El escenario deja de correr hasta el siguiente mes. Puedes reducir frecuencia de Scheduled o pagar $9/mes para 10,000 ops. Para AI 101 el plan gratuito es suficiente.

### P: ¿Por qué necesito filtro de asunto en Gmail si ya estoy filtrando?
**R:** Sin filtro, el trigger procesa CADA correo que llega. Agotás las operaciones en 1-2 días.

### P: ¿Qué hago si mi Instant Trigger no dispara?
**R:** 1) Click "Run once" en el trigger para activarlo, 2) Verificá que el filtro no sea demasiado restrictivo, 3) Revisá la sección History del escenario.

### P: ¿Puedo usar otra plataforma en vez de Make (Zapier, n8n)?
**R:** El concepto es el mismo pero el Lab asume Make. Si ya tenés otra, el patrón funciona igual — pero los screenshots de la entrega no coincidirán.

---

## 🔗 Conexiones del Curriculum

### Esta clase construye sobre:

| Clase | Concepto | Cómo se conecta |
|-------|----------|-----------------|
| 01 | Gem y brief | Sin brief, no sabrías qué filtro de Gmail ponerle al trigger |
| 02 | Sheet con 3 pestañas | Los 2 escenarios leen/escriben en VentasSemanaActual |
| 03 | Marcadores clasificados | Los Replace Text usan los nombres de la tabla de parámetros |

### Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "La próxima clase es la bisagra del curso. Todo lo que hicimos hasta hoy era construir el escenario sin IA. En Clase 5 agregamos Gemini API en dos puntos: el primer escenario procesará correos informales y extraerá datos estructurados (adiós al filtro rígido de asunto), y el segundo escenario generará los insights tipo IA de la tabla de parámetros. El sistema cobrará inteligencia."

**Pre-work / Tarea implícita:** crear API key de Gemini gratis en [Google AI Studio](https://aistudio.google.com/){:target="_blank"} antes de la próxima clase. Sin la API key no se puede hacer el lab.

---

## 📊 Test Diagnóstico del Módulo

### Logística (15 min en clase)

| Actividad | Tiempo | Qué hacer |
|-----------|--------|-----------|
| Test diagnóstico | 15 min | Proyectar countdown, ambiente silencioso |

### Durante el test

> "Tienen 15 minutos. Es individual y a libro cerrado. Recuerden: esto NO afecta su calificación — es para que nosotros sepamos qué temas necesitan más práctica antes del Módulo 2."

**Tips:**
- Proyectar timer en pantalla.
- Circular sin presionar.
- No responder preguntas sobre contenido durante el test.

### Revisión de resultados

Las preguntas y clave están en `test/questions.md`. Revisar en la siguiente clase (al inicio) solo las preguntas con <60% de acierto.

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos estudiantes completaron los 2 escenarios end-to-end en clase?
- ¿Quiénes siguen sin entender la diferencia Instant vs Scheduled? (seguimiento en Clase 5)
- ¿Hubo casos donde el PDF llegó pero con diseño roto? (candidatos para refinar plantilla en Clase 7)
- ¿Ya todos tienen API key de Gemini para Clase 5?
