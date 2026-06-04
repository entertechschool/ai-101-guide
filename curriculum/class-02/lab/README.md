# Lab 02: Registro automático de facturas

## 🎯 Objetivo

Construir tu **primer escenario en Make** conectando tu cuenta Google vía OAuth: cuando subes una factura a una carpeta de Drive, se registra sola una fila en un Google Sheet. **Sin IA aún.**

---

## 🔑 Conceptos Clave

- **Escenario de Make** — flujo visual sin código: trigger → módulos → acción.
- **OAuth** — el permiso que le das a Make para usar tu Google sin compartir tu contraseña.
- **Google Cloud Project** — genera el Client ID + Secret que Make necesita para conectar.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Cuenta de Make activa | Entra a [make.com](https://make.com/){:target="_blank"} y ves tu dashboard |
| ☐ | Cuenta de Google | La misma que usas para Drive y Sheets |
| ☐ | Acceso a Google Cloud | Abre [console.cloud.google.com](https://console.cloud.google.com/){:target="_blank"} |

---

## Mini-proyecto: registro automático de facturas

> Vas a armar el flujo **Drive → Sheets** de punta a punta. Al final, cada archivo nuevo en una carpeta de Drive aparece como fila en tu Sheet.

### Paso 1: Crea tu Google Cloud Project (Client ID + Secret)

En [console.cloud.google.com](https://console.cloud.google.com/){:target="_blank"}:

1. **Crea un proyecto** nuevo: `AI101-Make-[<!-- tu nombre -->]`.
2. Ve a **APIs y servicios → Biblioteca** y habilita **Google Drive API** y **Google Sheets API**.
3. Configura la **Pantalla de consentimiento OAuth** (tipo "Externo", nombre de la app, tu correo).
4. Ve a **Credenciales → Crear credenciales → ID de cliente de OAuth → Aplicación web**.
5. En **URIs de redireccionamiento autorizados** pega la que indica Make:
   ```
   https://www.integromat.com/oauth/cb/google-restricted
   ```
6. Copia el **Client ID** y el **Client Secret** — los pegarás en Make.

✓ **Verificación:** Tienes Client ID y Secret a la mano y las dos APIs habilitadas.

### Paso 2: Crea la carpeta de entrada en Drive

En Google Drive, crea una carpeta llamada **`Facturas-Entrada`**. Aquí subirás las facturas que el flujo va a detectar.

### Paso 3: Crea el Sheet de registro

Crea un Google Sheet llamado **`Facturas-Registro`** con estas columnas en la fila 1:

| Nombre archivo | Fecha de subida | Link |
|----------------|-----------------|------|

### Paso 4: Arma el escenario en Make

En Make → **+ Create a new scenario**. Nómbralo `Facturas: Drive → Sheet`.

**4.1 Trigger — Google Drive › Watch Files**
- Al conectar, elige **crear una conexión** y pega tu **Client ID + Secret** del Paso 1.
- **Folder:** `Facturas-Entrada`
- **Watch:** archivos creados en esa carpeta

**4.2 Acción — Google Sheets › Add a Row**
- **Spreadsheet:** `Facturas-Registro`
- **Values:**
  - `Nombre archivo` → `{{1.name}}`
  - `Fecha de subida` → `{{1.createdTime}}`
  - `Link` → `{{1.webViewLink}}`

✓ **Verificación:** El escenario tiene 2 módulos conectados: Drive (verde) → Sheets.

### Paso 5: Prueba con Run once

1. Click en **Run once**.
2. Sube una factura (PDF o imagen) a la carpeta `Facturas-Entrada`.
3. Observa los módulos ejecutarse y revisa tu Sheet.

✓ **Verificación:** Aparece una fila nueva en `Facturas-Registro` con el nombre, fecha y link del archivo.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué hace exactamente el trigger y qué hace la acción en tu escenario?**
2. **¿Por qué OAuth es más seguro que darle tu contraseña a Make?**

---

## Logros Adicionales (Opcional)

### 🟢 Activa el escenario
Cambia el toggle a **On** y configura el intervalo de chequeo (cada 15 min). Sube otra factura y verás la fila aparecer sola, sin Run once.

### 🟡 Agrega una columna "Estado"
Suma una columna `Estado` al Sheet y mapea un valor fijo `"Registrada"`. Preview de cómo más adelante el flujo marcará el avance.

### 🔴 Renombra el archivo con fecha
Investiga el módulo **Google Drive › Rename a File** para que cada factura quede con un nombre estandarizado. Lo retomamos en la Sesión 6.

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] Escenario en Make con Drive Watch Files → Sheets Add a Row
- [ ] Conexión Google funcionando (con tu Client ID/Secret)
- [ ] Al subir una factura a Drive, aparece una fila en `Facturas-Registro`

> 📸 Ten a la mano la pantalla de Make con el escenario corrido (módulos en verde) y el Sheet con la fila nueva.
