# Guía del Facilitador - Sesión 03: API key de Gemini

> Tiempo de lectura: 7 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **API**: puente que permite a una app pedirle algo a otra de forma estructurada.
- **API key**: llave personal y secreta para usar la API; se asocia a tu cuenta.
- **Connection (Make)**: credencial guardada una vez y reutilizada; más segura que pegar la key suelta.
- **Flash vs Pro**: Flash es rápido/económico (ideal para leer facturas); Pro es más capaz/caro.

---

## 🔗 Analogías Útiles

**API ⟷ mesero del restaurante:**
No entras a la cocina a cocinar. Le pides al mesero (la API) en un formato entendible, y te trae el plato. Tu escenario le pide a Gemini vía la API y recibe la respuesta.

**API key ⟷ tu credencial de socio:**
El gimnasio no te deja entrar con la contraseña de otro. Tu API key te identifica a ti, cuenta tu uso y se puede revocar. Por eso no se comparte.

**Connection ⟷ tarjeta guardada en la app de delivery:**
Cargas tu método de pago una vez y todos tus pedidos lo reutilizan. La Connection de Make hace lo mismo con tu API key.

---

## 📚 Contexto para Compartir

### Por qué la IA "cuesta" cada vez que la usas

Cada llamada a la API consume recursos de cómputo. Por eso la key se asocia a una cuenta con límites (el free tier de Gemini alcanza de sobra para el curso). Es útil que el estudiante entienda que automatizar con IA tiene un costo por uso, aunque hoy sea gratis.

> **Para contar en clase:** "Cuando la IA vive dentro de un flujo que corre solo, cada ejecución es una llamada. Por eso elegimos Flash: hace el trabajo a una fracción del costo."

### Connection vs API key directa

Pegar la key en cada módulo la expone (aparece en capturas, se duplica, es difícil de rotar). La Connection la guarda cifrada y se reutiliza. Es la diferencia entre una práctica amateur y una profesional.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "Cuando una app dice 'conecta tu cuenta de OpenAI/Gemini con tu API key', ¿qué crees que es esa key?"

**Respuesta esperada:** Una llave personal y secreta que identifica tu cuenta y permite usar el servicio (y cuenta tu consumo).

**Script post-respuestas:**
```
Facilitador: "Esa llave es lo que hoy van a generar. Es lo que conecta CUALQUIER IA con sus herramientas.
La tratan como una contraseña: nunca se comparte."
```

### Demo Principal

**Qué mostrar:** generar una API key en AI Studio y agregar el módulo Gemini al escenario de facturas en vivo, extrayendo el proveedor.

**Script sugerido:**
```
Facilitador: "Genero la key acá en AI Studio... la copio."
[Crea la Connection en Make con la key]
Facilitador: "Ahora pongo a Gemini entre Drive y el Sheet."
[Agrega el módulo, prompt 'extrae el proveedor', adjunta el archivo]
Facilitador: "Subo una factura... miren la columna Proveedor llenándose sola."
```

**Plan B (si AI Studio o Make fallan):** ten una Connection ya creada y el escenario armado para mostrar el Run once.

### Transición al Mini-proyecto

**Momento crítico:** el miedo a "exponer" la key. Tranquilízalos: la Connection la protege.

**Script sugerido:**
```
Facilitador: "Generar la key es un click. Guardarla como Connection la mantiene segura.
Vamos juntos: primero la key, después la conexión, después el módulo."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "¿Flash o Pro?"

Durante la teoría, lanza tareas y el grupo responde:

```
"Leer 500 facturas simples por mes" → Flash
"Analizar un contrato legal complejo" → Pro
"Extraer el proveedor de una factura" → Flash
"Redactar un informe estratégico largo" → Pro
```

### Dinámica 2: "Checkpoint de la key"

Pide que peguen un ✅ en el chat cuando tengan su API key creada y la Connection guardada. Así nadie se queda atrás antes de armar el módulo.

---

## 💡 Ejemplos Listos para Usar

### Prompt de extracción (para el módulo Gemini)

```
Lee esta factura y devuelve SOLO el nombre del proveedor
(la empresa que emite la factura), sin texto adicional.
```

**Tip:** pedir "SOLO el nombre, sin texto adicional" evita que Gemini agregue frases tipo "El proveedor es...". En la Sesión 4 formalizamos esto con JSON.

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Error 400 / API key inválida" | Key mal copiada o con espacios | Volver a copiarla completa desde AI Studio |
| "El módulo Gemini no ve la factura" | No adjuntó el archivo del módulo Drive | Mapear el campo de archivo/imagen del módulo Drive al de Gemini |
| "Gemini responde con texto de más" | El prompt no restringe la salida | Agregar "SOLO el nombre, sin texto adicional" |
| "No encuentro el módulo de Gemini" | Busca con otro nombre | Buscar "Google AI" o "Gemini" en el buscador de módulos |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Explica qué es una API key y por qué es secreta
- Sabe por qué una Connection es mejor que pegar la key suelta
- Elige Flash para tareas simples sin dudar

### El estudiante NECESITA AYUDA cuando:
- Quiere pegar la key en cada módulo
- No logra adjuntar la factura al módulo de Gemini
- Confunde la API key con la contraseña de su cuenta Google

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Pueden explicar API key y Connection | Tomar 1 respuesta buena y seguir |
| 55 | Mini-proyecto listo | Sheet registra el Proveedor extraído por Gemini | Usar el escenario pre-armado del facilitador para que todos vean el resultado |
| 60 | Cierre | Cada quien confirma su columna Proveedor llena | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo se atrasa con la key:** háganlo todos al mismo tiempo, pantalla compartida.
- **Si alguien termina antes:** propón el Logro 🟢 (extraer el monto también).
- **Si el módulo Gemini no lee el archivo:** revisa que el trigger de Drive entregue el archivo (no solo metadatos) y que esté bien mapeado.
- **Preguntas sobre múltiples datos:** "Eso es exactamente la próxima sesión — pedirle a la IA varios datos en JSON ordenado."

---

## ❓ Preguntas Frecuentes

### P: ¿La API key de Gemini es gratis?
**R:** Sí, el free tier de Google AI Studio alcanza de sobra para el curso. No requiere tarjeta.

### P: ¿Tengo que crear una key nueva en cada escenario?
**R:** No. Generas una key, la guardas como Connection en Make y la reutilizas en todos los escenarios.

### P: ¿Por qué Flash y no Pro?
**R:** Para leer facturas, Flash es rápido y mucho más económico. Pro se reserva para análisis complejos.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 01 | Prompt (rol + tarea + contexto + formato) | El prompt del módulo Gemini aplica la misma anatomía |
| 02 | Escenario Drive → Sheet | Insertamos Gemini en medio de ese flujo |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "Hoy Gemini extrajo UN dato: el proveedor. La próxima sesión le pedimos varios datos a la vez —vendedor, cliente, monto, fecha— y aprendemos a recibirlos ordenados con JSON y Parse JSON, para que cada uno caiga en su columna."

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos lograron la columna Proveedor llena por la IA?
- ¿Dónde se trabaron: generar la key, la Connection o adjuntar el archivo?
- ¿Quiénes quedaron sin Gemini funcionando? (seguimiento antes de la Sesión 4, que depende de esto)
