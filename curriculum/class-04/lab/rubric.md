# Criterio de evaluación - Sesión 04: Extracción de ventas desde Gmail

> 📋 **Documento interno para el facilitador**
>
> En v3 la práctica se evalúa **en clase: 0 (no hizo) / 100 (sí hizo)**. No hay rúbrica ponderada ni entrega post-clase. Este documento define qué cuenta como "hizo" (100).

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Sesión** | 04 — JSON + Parse JSON |
| **Mini-proyecto** | Extracción de ventas desde Gmail |
| **Modelo de evaluación** | 0 / 100 (en clase) |

---

## Qué cuenta como "hizo" (100)

El estudiante obtiene **100** si, durante la sesión, muestra su escenario funcionando con **todo** lo siguiente:

- [ ] **System prompt** que pide a Gemini responder SOLO en JSON con los campos definidos (vendedor, cliente, producto, monto, fecha)
- [ ] **Data Structure** creado en Make (el molde del JSON)
- [ ] **Parse JSON** conectado, mostrando las variables separadas
- [ ] **Sheets Add a Row** con cada variable mapeada a su columna
- [ ] Al enviar un correo de venta de prueba, el Sheet `Ventas` recibe una **fila estructurada** (cada dato en su columna)

> Obtiene **0** si no llega a mostrar el flujo produciendo una fila estructurada en clase.

---

## Señales de un buen resultado

- El JSON sale limpio sin texto envuelto (prompt bien restringido).
- El `monto` llega como número (tipo correcto en el Data Structure).
- El flujo funciona con un correo informal real, no solo con un texto perfecto.

---

## Errores que NO penalizan

- Que el correo de prueba sea sencillo (el objetivo es que el flujo funcione, no la complejidad del correo).
- Pequeños ajustes de formato de fecha — se pulen en la Sesión 6 (flujo robusto).

---

## Notas para el facilitador

1. Lo esencial es que el estudiante **conecte Gemini → Parse JSON → Sheet** y vea la fila estructurada. Ese es el aprendizaje de la sesión.
2. Si alguien no logra el flujo completo en clase, déjalo con el escenario pre-armado del facilitador para que vea el resultado y lo replique después (sin nota, pero con comprensión).
3. El test diagnóstico (`test/`) es aparte y **no** afecta la calificación.
