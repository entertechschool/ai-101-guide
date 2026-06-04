# Lab 06: Flujo completo de facturas

## 🎯 Objetivo

Unir las piezas de las sesiones anteriores en **un solo flujo robusto** (Drive → IA → Sheets → Docs → Email) con **filtros, un router y manejo de errores**, capaz de aguantar el mundo real.

---

## 🔑 Conceptos Clave

- **Watch vs Schedule** — trigger por evento o programado.
- **Filtro / Router** — lógica condicional: qué procesar y por qué ruta.
- **Error handler + Logs** — que el flujo avise si falla y deje rastro.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Escenarios de Sesiones 2-5 | Drive→Sheet, Gemini, Parse JSON, plantilla |
| ☐ | Sheet de facturas con datos | Tiene proveedor, monto, fecha |
| ☐ | Plantilla de reporte (Sesión 5) | Con placeholders |
| ☐ | Un par de archivos "difíciles" | Un no-PDF, una factura sin total |

---

## Mini-proyecto: flujo completo de facturas

> Vas a integrar todo en un escenario y hacerlo robusto.

### Paso 1: Integra S2-S5 en un solo escenario

Encadena los módulos en orden:

```
Drive Watch Files → Gemini (extrae JSON) → Parse JSON → Sheets Add a Row
   → (al cierre del mes) Search Rows → Create from Template → Export PDF → Gmail Send
```

### Paso 2: Agrega filtros

- Entre Drive y Gemini, agrega un **filtro**: `File extension = pdf` **AND** procesar solo facturas.
- Esto evita gastar operaciones (y llamadas a la IA) en archivos que no son facturas.

✓ **Verificación:** Un archivo que no es PDF se salta sin procesarse.

### Paso 3: Agrega un router

Agrega un **Router** después del Parse JSON con dos rutas:
- **Ruta A — factura grande** (`monto > 1000`): además de registrar, envía una alerta al jefe.
- **Ruta B — factura normal**: solo registra en el Sheet.

✓ **Verificación:** Una factura grande dispara la alerta; una normal no.

### Paso 4: Agrega manejo de errores

1. Click derecho en el módulo más frágil (Gemini) → **Add error handler → Resume**.
2. En el handler, agrega **Gmail › Send an Email** al jefe:
   - **Subject:** `❌ Error en el flujo de facturas`
   - **Body:** `Falló el módulo [nombre]. Revisar Make History.`
3. (Opcional) Registra el error en una pestaña `Logs` del Sheet (fecha, estado, módulo).

✓ **Verificación:** Si un módulo falla, llega la alerta y el flujo sigue con el siguiente item.

### Paso 5: Prueba con casos límite

- Sube un archivo que **no** es PDF → debe saltarse (filtro).
- Sube una factura **sin total** → observa cómo lo maneja.
- Sube una factura **grande** → debe llegar la alerta (router).
- Revisa el **History** de Make: verde = éxito, rojo = error.

✓ **Verificación:** El flujo procesa lo válido, salta lo inválido y avisa cuando algo se rompe.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué caso límite te sorprendió más al probar?**
2. **¿Por qué un error handler "Resume" es mejor que detener todo el flujo?**

---

## Logros Adicionales (Opcional)

### 🟢 Nombre de archivo con fecha
En Export as PDF, usa `Reporte_{{formatDate(now; "YYYY-MM-DD")}}.pdf` para ordenar cronológicamente.

### 🟡 Carpeta de Backups
Agrega un Upload a File a una carpeta `Backups` con una copia de cada PDF generado.

### 🔴 Dashboard de Logs
Crea un gráfico en la pestaña `Logs` que muestre éxitos vs errores por semana.

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] Un solo escenario que integra Drive → IA → Sheets → Docs → Email
- [ ] Al menos un filtro y un router funcionando
- [ ] Error handler con notificación configurado
- [ ] Prueba con un caso límite (no-PDF o factura sin total)

> 📸 Ten a la mano el escenario completo (con filtro, router y handler visibles) y el History con una corrida en verde.
