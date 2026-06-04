# Lab 04: Extracción de ventas desde Gmail

## 🎯 Objetivo

Hacer que la IA devuelva **varios datos juntos en JSON** y que cada campo caiga solo en su columna: cuando un vendedor envía un correo informal con una venta, Gemini devuelve JSON, **Parse JSON** lo convierte en variables y el Sheet `Ventas` se llena estructurado.

---

## 🔑 Conceptos Clave

- **JSON** — formato de datos en pares clave-valor que las apps entienden.
- **Data Structure** — el "molde" en Make que describe cómo viene el JSON.
- **Parse JSON** — módulo que convierte el texto JSON en variables mapeables.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Connection a Gemini en Make (Sesión 3) | Disponible al agregar un módulo Gemini |
| ☐ | Cuenta de Gmail | Para enviarte correos de venta de prueba |
| ☐ | Google Sheet con pestaña `Ventas` | Columnas: vendedor, cliente, producto, monto, fecha |

---

## Mini-proyecto: ventas desde Gmail

> Vas a armar un escenario que vigila correos de ventas, le pide a Gemini un JSON, lo parsea y lo guarda estructurado.

### Paso 1: Configura el trigger Gmail Watch

En un escenario nuevo (`Ventas: Gmail → Sheet`), agrega **Gmail › Watch Emails**:
- **Folder:** Inbox
- **Filter by subject contains:** `Venta` (o el asunto que definas para los vendedores)

### Paso 2: Diseña el system prompt para Gemini

Agrega el módulo **Gemini** después de Gmail. En el prompt, pide JSON explícito:

```
Eres un asistente que extrae datos de correos de ventas.
Devuelve SOLO un JSON con estos campos, sin texto adicional:
{ "vendedor": "", "cliente": "", "producto": "", "monto": 0, "fecha": "YYYY-MM-DD" }

CORREO:
{{1.text}}
```

> `{{1.text}}` es el cuerpo del correo del módulo Gmail.

✓ **Verificación:** Al probar, Gemini responde con un JSON válido.

### Paso 3: Crea el Data Structure (el molde)

Agrega el módulo **JSON › Parse JSON**. Al crear el Data Structure:
- **Generate** desde un ejemplo: pega una respuesta típica de Gemini, o
- Define los campos a mano:

| Campo | Tipo |
|-------|------|
| vendedor | Text |
| cliente | Text |
| producto | Text |
| monto | Number |
| fecha | Date |

### Paso 4: Conecta Parse JSON

- **JSON string:** la salida de texto del módulo Gemini.
- Parse JSON genera las variables `vendedor`, `cliente`, `producto`, `monto`, `fecha`.

✓ **Verificación:** El módulo Parse JSON muestra las variables separadas.

### Paso 5: Mapea las variables al Sheet "Ventas"

Agrega **Google Sheets › Add a Row** y mapea cada columna:
- `vendedor` → `{{parse.vendedor}}`
- `cliente` → `{{parse.cliente}}`
- `producto` → `{{parse.producto}}`
- `monto` → `{{parse.monto}}`
- `fecha` → `{{parse.fecha}}`

### Paso 6: Prueba con un correo de venta

Envíate un correo informal, por ejemplo:

```
Asunto: Venta del día
Hoy Ana cerró a Acme S.A. por 1500 soles en consultoría mensual, cliente nuevo.
```

Corre **Run once** y revisa el Sheet.

✓ **Verificación:** El Sheet `Ventas` recibe una fila con cada campo en su columna, sin importar el formato del correo.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Por qué el Data Structure evita que se guarde basura en el Sheet?**
2. **¿Qué pasaría si la IA devolviera texto libre en vez de JSON?**

---

## Logros Adicionales (Opcional)

### 🟢 Agrega un campo "tipo"
Suma `tipo` (Nuevo / Recurrente) al JSON y al Data Structure. Observa cómo Gemini lo infiere del texto.

### 🟡 Prueba 3 correos con formatos distintos
Envía correos formales, informales y con typos. Verifica que el JSON sale consistente igual.

### 🔴 Maneja el campo faltante
¿Qué pasa si el correo no menciona el monto? Ajusta el prompt para que devuelva `null` y observa cómo lo maneja Parse JSON.

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] System prompt que pide JSON con los 5 campos
- [ ] Data Structure + módulo Parse JSON funcionando
- [ ] Al enviar un correo de venta, el Sheet `Ventas` se llena con cada campo en su columna

> 📸 Ten a la mano el escenario corrido (Gmail → Gemini → Parse JSON → Sheets) y el Sheet con la fila estructurada.

---

> 📌 Esta sesión cierra el bloque de "piezas técnicas" del sistema. En la Sesión 4 también puede aplicarse el **test diagnóstico** del primer bloque (ver carpeta `test/`) — es de control interno y no afecta la calificación.
