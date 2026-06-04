# Lab 03: La IA extrae el proveedor

## 🎯 Objetivo

Sumar **Gemini** al escenario de la Sesión 2: cuando entra una factura a Drive, la IA lee el documento, extrae el **proveedor** y lo registra en una columna nueva del Sheet.

---

## 🔑 Conceptos Clave

- **API key** — tu llave personal y secreta para usar Gemini, generada en Google AI Studio.
- **Connection en Make** — credencial guardada una vez y reutilizada en cualquier escenario.
- **Gemini Flash** — modelo rápido y económico, ideal para leer documentos.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Escenario Drive → Sheet (Sesión 2) | Corre y registra filas al subir una factura |
| ☐ | Cuenta de Make activa | Entras a tu dashboard |
| ☐ | Cuenta de Google | Para acceder a Google AI Studio |

> ⚠️ Sin el escenario de la Sesión 2 funcionando no puedes hacer este lab. Complétalo primero.

---

## Mini-proyecto: la IA lee la factura y extrae el proveedor

> Vas a insertar un módulo de Gemini entre el trigger de Drive y la fila del Sheet.

### Paso 1: Genera tu API key en Google AI Studio

1. Ve a [aistudio.google.com/apikey](https://aistudio.google.com/apikey){:target="_blank"}.
2. Click **Create API key** → elige tu proyecto.
3. **Copia la key** (se ve como `AIzaSy...`) y guárdala en un lugar seguro.

> ⚠️ Nunca compartas tu API key (ni en capturas, repos o chats). Es como una contraseña.

✓ **Verificación:** Tienes tu API key copiada.

### Paso 2: Crea la Connection a Gemini en Make

1. En tu escenario, agrega un módulo **Google AI (Gemini)**.
2. Al pedir conexión, elige **Add** y pega tu **API key**.
3. Nombra la conexión `Gemini - Curso AI101` para reutilizarla después.

✓ **Verificación:** La conexión queda guardada y disponible en Make.

### Paso 3: Agrega el módulo Gemini al escenario

Coloca el módulo de Gemini **después del trigger de Drive** y **antes del Sheets Add a Row**:

```
Drive Watch Files  →  Gemini (leer factura)  →  Sheets Add a Row
```

### Paso 4: Pídele que extraiga el proveedor

En el módulo de Gemini:
- **Model:** `gemini-2.5-flash`
- **Prompt:**
  ```
  Lee esta factura y devuelve SOLO el nombre del proveedor (la empresa
  que emite la factura), sin texto adicional.
  ```
- Adjunta el archivo de la factura desde el módulo de Drive (campo de archivo/imagen).

✓ **Verificación:** Al probar, Gemini responde con el nombre del proveedor.

### Paso 5: Mapea el proveedor a una columna nueva

1. En tu Sheet `Facturas-Registro`, agrega una columna **`Proveedor`**.
2. En el módulo **Sheets Add a Row**, mapea:
   - `Proveedor` → la salida de texto del módulo Gemini
3. Corre **Run once** y sube una factura de prueba.

✓ **Verificación:** El Sheet registra la fila con la columna **Proveedor** llena por la IA.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Por qué una Connection es más segura que pegar la API key en cada módulo?**
2. **¿Para esta tarea conviene Flash o Pro? ¿Por qué?**

---

## Logros Adicionales (Opcional)

### 🟢 Extrae un segundo dato
Pídele a Gemini también el **monto total** y mapéalo a otra columna. (Cuando sean varios datos juntos, en la Sesión 4 lo haremos ordenado con JSON.)

### 🟡 Prueba con una factura "difícil"
Sube una factura con formato raro o foto borrosa. ¿Acierta? Anota dónde falla — útil para la Sesión 6.

### 🔴 Compara Flash vs Pro
Duplica el módulo con `gemini-2.5-pro` y compara la calidad y velocidad de la extracción.

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] API key generada y guardada como Connection en Make
- [ ] Módulo Gemini en el escenario, entre Drive y Sheets
- [ ] Al subir una factura, el Sheet registra el **Proveedor** extraído por la IA

> 📸 Ten a la mano el escenario con el módulo Gemini en verde y el Sheet con la columna Proveedor llena.
