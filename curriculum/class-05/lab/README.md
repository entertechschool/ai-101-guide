# Lab 05: Gemini API + 2 flujos completos

## 🎯 Objetivos

1. Obtener API key de Gemini gratis y configurar el módulo HTTP en Make.
2. Agregar IA al flujo instantáneo: correo informal → Gemini extrae JSON → Sheet con datos estructurados.
3. Activar el flujo semanal scheduled con Gemini generando insights (marcadores tipo 3) + alimentando Historico.

---

## 🔑 Conceptos Clave

- **Gemini API** — servicio gratuito (1,500 req/día) para llamar a Gemini desde cualquier programa.
- **Módulo HTTP en Make** — módulo genérico que hace llamadas POST con URL, headers y body JSON.
- **Prompt JSON estructurado** — pedir a Gemini que responda en formato `{clave: valor}` para mapear directo a marcadores.

---

## ⚙️ Setup Inicial

Esta sesión integra todo lo construido en M1 + la API de Gemini. Verifica:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | API key de Gemini activa | Copiada de [aistudio.google.com/apikey](https://aistudio.google.com/apikey){:target="_blank"} |
| ☐ | Escenario 1 de Make (Gmail→Sheet) | Activo de la Clase 4 |
| ☐ | Escenario 2 de Make (Sheet→Slides→PDF) | Run once funcionó en Clase 4 |
| ☐ | Tabla de parámetros con marcadores tipo IA | De la Clase 3 |

> ⚠️ Sin API key no se puede hacer el lab. Obténla primero si no la tienes.

---

## Actividad 1: Obtén API key y haz tu primera llamada (45 min)

### 1.1 Obtén tu API key

1. Ve a [aistudio.google.com/apikey](https://aistudio.google.com/apikey){:target="_blank"}
2. Click "Create API key" → elige proyecto default
3. **Copia la key** — se ve algo como `AIzaSyA...` (larga)

> ⚠️ Nunca compartas tu API key públicamente (repos, capturas, chats). Es como una contraseña.

### 1.2 Prueba en Google AI Studio

Antes de meterla en Make, prueba tu prompt en el playground:

1. Ve a [aistudio.google.com](https://aistudio.google.com/){:target="_blank"}
2. Nuevo chat → elige modelo `gemini-2.0-flash` (gratis y rápido)
3. Pega este prompt de prueba:

```
Eres un asistente que extrae datos de correos de ventas.
Te voy a dar un correo informal y debes devolver JSON con estos campos:
{ "fecha": "YYYY-MM-DD", "vendedor": "nombre", "cliente": "nombre",
  "producto": "nombre", "monto": numero, "tipo": "Nuevo" | "Recurrente",
  "descripcion": "resumen en 1 línea" }

CORREO:
"Hola, hoy Juan cerró a Industrias López por 3500 soles en consultoría mensual,
es cliente recurrente desde enero. - sent from iPhone"
```

4. Verifica que Gemini responde con JSON válido.

### 1.3 Agrega módulo HTTP en Make

Vuelve al **Escenario 1** en Make (Gmail → Sheet de la Clase 4):

1. Después del módulo Gmail, **+ Add a module → HTTP → Make a request**
2. Configuración:
   - **URL:** `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=TU_API_KEY_AQUI`
   - **Method:** `POST`
   - **Headers:** `Content-Type: application/json`
   - **Body type:** Raw → JSON
   - **Request content:**

```json
{
  "contents": [{
    "parts": [{
      "text": "Extrae datos del siguiente correo y responde SOLO en JSON con los campos fecha, vendedor, cliente, producto, monto, tipo, descripcion:\n\n{{1.text}}"
    }]
  }]
}
```

> 💡 `{{1.text}}` es el cuerpo del correo del módulo Gmail anterior.

### 1.4 Parsea la respuesta y mapea al Sheet

1. Agrega módulo **JSON → Parse JSON** después del HTTP
   - **Data structure:** Generate from sample → pega una respuesta típica de Gemini
2. Modifica el módulo **Google Sheets → Add a row** final:
   - Fecha → `{{parse.fecha}}`
   - Vendedor → `{{parse.vendedor}}`
   - Cliente → `{{parse.cliente}}`
   - Producto → `{{parse.producto}}`
   - Monto → `{{parse.monto}}`
   - Tipo → `{{parse.tipo}}`
   - Descripción → `{{parse.descripcion}}`

### 1.5 Prueba con 3 correos informales distintos

Envía 3 correos con formatos diferentes (formales, informales, con typos). Verifica que el Sheet recibe filas bien estructuradas.

✅ **Checkpoint:** Los 3 correos generan 3 filas completas y bien estructuradas en el Sheet, sin importar el formato del correo.

---

## Actividad 2: Genera insights para marcadores tipo IA (40 min)

### 2.1 Agrega HTTP al escenario 2

Vuelve al **Escenario 2** (Sheet→Slides→PDF). Antes de los módulos Replace Text, agrega un módulo **HTTP → Make a request**:

- **URL:** mismo endpoint de Gemini
- **Method:** POST
- **Body JSON:** pide a Gemini que devuelva los marcadores tipo 3 en un solo JSON

### 2.2 Prompt para generar insights

```json
{
  "contents": [{
    "parts": [{
      "text": "Eres un analista de ventas. Analiza los datos de esta semana y devuelve SOLO JSON con estos campos:\n{\n  \"resumen_ejecutivo\": \"...\",\n  \"hallazgo_1\": \"...\",\n  \"hallazgo_2\": \"...\",\n  \"hallazgo_3\": \"...\",\n  \"riesgo_1\": \"...\",\n  \"riesgo_2\": \"...\",\n  \"oportunidad_1\": \"...\",\n  \"accion_1\": \"...\",\n  \"accion_2\": \"...\"\n}\n\nDATOS SEMANA:\n{{datos_formateados_del_sheet}}\n\nMETA SEMANAL: {{config.meta}}\nSEMANA ANTERIOR: {{historico.ventas_anterior}}"
    }]
  }]
}
```

### 2.3 Parse + mapea a cada marcador

1. Módulo **Parse JSON** después del HTTP
2. En cada **Replace Text** de marcadores tipo 3:
   - `{{resumen_ejecutivo}}` → `{{parse.resumen_ejecutivo}}`
   - `{{hallazgo_1}}` → `{{parse.hallazgo_1}}`
   - ... (todos los marcadores tipo 3)

### 2.4 Run once y verifica

Ejecuta el escenario manualmente. El PDF debe llegar ahora con los marcadores tipo 3 llenos con insights reales (no `{{hallazgo_1}}` literal).

✅ **Checkpoint:** El PDF del correo tiene los marcadores tipo IA llenos con texto coherente y específico a tus datos de la semana.

---

## Actividad 3: Activa el flujo semanal scheduled + Historico (30 min)

### 3.1 Cambia el trigger a Scheduled

En el Escenario 2:

1. Click en el módulo trigger (primero) → **Scheduled**
2. Configuración:
   - **Interval:** Weekly
   - **Day:** Friday
   - **Time:** 16:00

### 3.2 Agrega Add a row al Historico al cierre del flujo

Después del módulo Send Email, agrega **Google Sheets → Add a row**:

- **Spreadsheet:** tu Sheet
- **Sheet:** `Historico`
- **Values:**
  - Semana → `{{formatDate(now; "DD-MM")}}` o similar
  - Ventas_Total → valor calculado
  - Clientes_Nuevos → valor calculado
  - Ticket_Promedio → valor calculado
  - Meta_Cumplida_Pct → valor calculado

### 3.3 Activa el scheduled

Toggle "On" del escenario 2. Ahora correrá automáticamente cada viernes 4pm.

### 3.4 Activa también el escenario instantáneo

Verifica que el Escenario 1 (Gmail → Gemini → Sheet) también esté activo.

### 3.5 Run once de prueba completa

Ejecuta manualmente el escenario 2 para validar que:
- Genera el PDF con insights
- Lo envía por correo
- Agrega una fila al Historico

✅ **Checkpoint:** Sistema modelo completo activo: Escenario 1 instantáneo + Escenario 2 scheduled + Historico alimentándose solo.

---

## 📁 Estructura Final del Proyecto

```
Make.com/
├── Escenario 1: Gmail → Gemini → Sheet (Instant, activo)
└── Escenario 2: Sheet → Gemini → Slides → PDF → Gmail + Historico (Scheduled viernes 4pm, activo)

Google AI Studio/
└── API Key activa (plan free: 1,500 req/día)

Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc
    ├── Tabla-de-Parámetros.doc (actualizada con prompts JSON)
    ├── sistema-reporte.xlsx
    ├── Reporte-Plantilla.slides
    └── Backups/ (si completaste desafío de C04)
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué te sorprendió más: la rapidez de Gemini API o la facilidad de mapear JSON a marcadores?**
2. **¿Qué insight de Gemini te pareció "plano" (útil en C06 cuando optimicemos prompts)?**
3. **¿Cuántas operaciones de Make consume ahora tu Escenario 2 completo?**

---

## Logros Adicionales (Opcional)

### 🟢 Prueba el modelo `gemini-2.0-flash-thinking-exp`
Cambia el modelo en la URL. Este modelo "piensa" antes de responder — compara calidad de insights vs el modelo rápido.

### 🟡 Prompt con few-shot
Agrega 2 ejemplos de input/output deseado dentro del prompt JSON. Observa mejora de calidad (preview de C06).

### 🔴 Guarda el prompt como variable
En Make, usa "Tools → Set multiple variables" al inicio del escenario para definir el prompt como variable. Facilita actualización sin entrar a cada HTTP.

---

## 📝 Entrega

### Checklist

- [ ] API key de Gemini configurada y funcionando
- [ ] Escenario 1 activo: procesa correos informales con Gemini y alimenta Sheet bien estructurado
- [ ] Escenario 2 activo: scheduled viernes 4pm, genera PDF con insights tipo IA llenos
- [ ] Historico se alimenta automáticamente al final del flujo semanal

### Entregable

📸 **Screenshots** mostrando:
- Escenario 1 con módulos: Gmail → HTTP (Gemini) → Parse JSON → Sheets Add Row
- Escenario 2 con módulos: Scheduled → Search Rows → HTTP (Gemini) → Parse JSON → Replace Text (múltiples) → Export PDF → Send Email → Add row Historico
- PDF llegando al correo con al menos 3 marcadores tipo IA visibles con texto coherente
- Tu cuenta de Google visible en al menos 2 de los screenshots

> ⚠️ El entregable debe mostrar tu cuenta para verificar autoría.
