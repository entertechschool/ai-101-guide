# Guía del Facilitador - Sesión 02: Make 101 + Google Cloud

> Tiempo de lectura: 8 minutos | Prepárate antes de clase

---

## 🔑 Conceptos Clave

- **Make**: plataforma no-code que conecta apps como bloques en un tablero.
- **Escenario**: un flujo automático; anatomía trigger → módulos → acción.
- **OAuth**: permiso que una app le da a otra sin compartir la contraseña; se materializa en un token.
- **Google Cloud Project**: contenedor que genera Client ID + Secret y habilita las APIs.

---

## 🔗 Analogías Útiles

**Escenario de Make ⟷ línea de producción:**
El trigger es la materia prima que entra (una factura nueva), los módulos son las estaciones que la transforman, y la acción es el producto final (una fila en el Sheet). Tú diseñas la línea una vez y produce sola.

**OAuth ⟷ llave de hotel:**
No le das al hotel la llave maestra de tu casa. Recepción te da una tarjeta que abre solo tu cuarto, por un tiempo, y se puede revocar. El token de OAuth es esa tarjeta: acceso limitado y revocable, nunca tu contraseña.

**Google Cloud Project ⟷ carnet de habilitación:**
Antes de que Make pueda tocar tu Drive, Google exige un "carnet" (Client ID + Secret) que dice quién es la app y qué puertas (APIs) tiene permitido tocar.

---

## 📚 Contexto para Compartir

### Por qué Make pide un Google Cloud Project

Para conexiones "restringidas" (Drive, Gmail), Google exige que la app se identifique con credenciales propias en lugar de usar las genéricas de Make. Suena técnico, pero el estudiante solo copia dos valores (Client ID + Secret). Vale la pena explicar el "por qué": es lo que mantiene seguro su Drive.

> **Para contar en clase:** "No es burocracia: es la diferencia entre darle a una app acceso total o acceso a una sola carpeta."

### Por qué no-code no es "menos serio"

Make ejecuta en producción procesos que antes requerían un programador. El estudiante no escribe código, pero sí diseña lógica. Es el mismo pensamiento, otra interfaz.

---

## 🎯 Momentos Clave de la Clase

### Pregunta Detonadora (Apertura)

**Pregunta:** "Cuando conectas una app con tu Google (ej: 'Iniciar sesión con Google'), ¿le estás dando tu contraseña?"

**Respuesta esperada:** No. Le das un permiso (token) vía OAuth; la contraseña nunca se comparte.

**Script post-respuestas:**
```
Facilitador: "Eso que hacen todo el tiempo —'entrar con Google'— es OAuth.
Hoy lo usamos al revés: ustedes le dan a Make permiso para trabajar en su Drive."
```

### Demo Principal

**Qué mostrar:** armar el escenario Drive → Sheets en vivo y correr Run once subiendo una factura.

**Script sugerido:**
```
Facilitador: "Pongo dos bloques: 'cuando entre un archivo a esta carpeta'..."
[Agrega Drive Watch Files]
Facilitador: "...'agrega una fila al Sheet'. Nada más."
[Agrega Sheets Add a Row, mapea name/date/link]
Facilitador: "Subo una factura... y miren el Sheet."
[La fila aparece]
```

**Plan B (si la conexión OAuth falla en vivo):** ten un escenario ya conectado en tu cuenta para mostrar el Run once sin depender de crear el Cloud Project en el momento.

### Transición al Mini-proyecto

**Momento crítico:** el Google Cloud Project asusta. Acompáñalos paso a paso y normaliza que es la parte más "técnica" del curso.

**Script sugerido:**
```
Facilitador: "El Cloud Project es lo más técnico que van a tocar en todo el curso.
Es copiar y pegar dos valores. Vamos juntos, pantalla compartida, paso a paso."
```

---

## 🎭 Dinámicas de Clase

### Dinámica 1: "Trigger o acción"

Durante la teoría, lanza ejemplos y el grupo responde "trigger" o "acción":

```
"Llega un correo nuevo" → trigger
"Se crea un PDF" → acción
"Aparece un archivo en Drive" → trigger
"Se agrega una fila al Sheet" → acción
```

### Dinámica 2: "Checkpoint del Cloud Project"

Antes de armar el escenario, pide que todos peguen en el chat un ✅ cuando tengan su Client ID listo. Así nadie queda atrás en el paso más frágil.

---

## 💡 Ejemplos Listos para Usar

### URI de redireccionamiento de Make

**Cuándo usarlo:** al crear las credenciales OAuth, el estudiante necesita esta URI exacta.

```
https://www.integromat.com/oauth/cb/google-restricted
```

**Tip:** si Make muestra una URI distinta en su pantalla de conexión, esa es la que manda — que copien la de su Make.

### Mapeo de columnas (para el Add a Row)

```
Nombre archivo  →  {{1.name}}
Fecha de subida →  {{1.createdTime}}
Link            →  {{1.webViewLink}}
```

---

## ⚠️ Errores Comunes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Make no me conecta con Google" | URI de redirección mal copiada o API no habilitada | Verificar la URI exacta y que Drive/Sheets API estén habilitadas |
| "Error 403 / acceso denegado" | Pantalla de consentimiento sin el correo como tester | Agregar su correo como usuario de prueba en la consent screen |
| "El trigger no detecta el archivo" | Carpeta equivocada o el escenario no corrió | Confirmar carpeta `Facturas-Entrada` y usar Run once |
| "No aparece la fila en el Sheet" | Mapeo vacío o Sheet/pestaña equivocada | Revisar que cada valor apunte a `{{1.algo}}` y la pestaña correcta |

---

## ✅ Señales de Comprensión

### El estudiante ENTIENDE cuando:
- Explica la diferencia entre trigger y acción con un ejemplo propio
- Sabe por qué OAuth no comparte la contraseña
- Puede decir para qué sirve el Client ID/Secret

### El estudiante NECESITA AYUDA cuando:
- Se traba creando el Cloud Project y abandona
- Confunde el trigger con la acción al armar el escenario
- Pega mal la URI de redirección

---

## 🎯 Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar | Si no cumple |
|--------|------------|--------------|--------------|
| 10 | Apertura completada | 3 preguntas respondidas en chat | Avanzar aunque no respondan todos |
| 30 | Fundamentos terminados | Pueden nombrar trigger → módulos → acción y qué es OAuth | Tomar 1 respuesta buena y seguir |
| 55 | Mini-proyecto listo | Escenario corre y aparece fila en el Sheet | Usar el escenario pre-conectado del facilitador para que todos vean el resultado |
| 60 | Cierre | Cada quien confirma su escenario funcionando | — |

---

## 🧑‍🏫 Tips de Facilitación

- **Si el grupo se atrasa en el Cloud Project:** comparte pantalla y háganlo todos al mismo tiempo, paso a paso.
- **Si alguien termina antes:** propón el Logro 🟢 (activar el escenario con intervalo).
- **Si la conexión OAuth falla en varios:** revisa primero la URI de redirección y que las APIs estén habilitadas — es el 90% de los casos.
- **Preguntas fuera de alcance (IA):** "Eso entra la próxima sesión, cuando Gemini lea la factura."

---

## ❓ Preguntas Frecuentes

### P: ¿El Google Cloud Project tiene costo?
**R:** No para este uso. Crear el proyecto y habilitar APIs de Drive/Sheets es gratis; no se factura nada por estas llamadas.

### P: ¿Make gratis alcanza?
**R:** Sí. El plan free (1,000 operaciones/mes) sobra para los escenarios del curso.

### P: ¿Tengo que volver a crear el Cloud Project en cada sesión?
**R:** No. Lo creas una vez; la conexión queda guardada en Make y se reutiliza en todos los escenarios.

---

## 🔗 Conexiones del Curriculum

### Esta sesión construye sobre:

| Sesión | Concepto | Cómo se conecta |
|--------|----------|-----------------|
| 01 | Output estructurado | El Sheet es el destino estructurado al que apuntará la IA |

### Conexión con la Próxima Sesión

Al cerrar, planta la semilla:

> "Hoy el flujo solo copia el nombre del archivo. La próxima sesión metemos a Gemini en medio: va a abrir la factura, leerla y extraer el proveedor. La IA entra a trabajar dentro de tu escenario."

---

## 🪞 Reflexión Post-Clase

### Preguntas para el facilitador:
- ¿Cuántos lograron conectar Google y correr el escenario?
- ¿Dónde se trabaron más: Cloud Project, URI de redirección o mapeo?
- ¿Quiénes quedaron sin conexión funcionando? (seguimiento antes de la Sesión 3, que depende de esto)
