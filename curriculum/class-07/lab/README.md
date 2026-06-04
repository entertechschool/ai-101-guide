# Lab 07: Tu proyecto integrador

## 🎯 Objetivo

Construir la **primera versión (v1)** de tu propio flujo automatizado, para un caso real de tu trabajo, aplicando todo lo aprendido: Make, Gemini, JSON, plantillas y robustez.

---

## 🔑 Conceptos Clave

- **Estructura del proyecto** — problema → solución → arquitectura.
- **Diagramar** — dibujar el flujo (trigger → módulos → output) antes de construir.
- **Iteración** — construir v1, probar con datos reales, refinar.

---

## ⚙️ Setup Inicial

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Método completo dominado | Sistema de facturas funcionando (Sesiones 2-6) |
| ☐ | Una idea de caso propio | Un proceso de tu trabajo que te quita tiempo |
| ☐ | Datos reales | 3-5 registros verídicos (o simulados realistas) |

> 💡 **Acompañamiento 1 a 1:** el instructor circula durante todo el lab. Pide ayuda cuando la necesites.

---

## Mini-proyecto: tu proyecto, paso a paso

### Paso 1: Elige tu caso real

Elige un proceso que haces seguido y te consume tiempo. Defínelo en 3 frases:

```
PROBLEMA:   [qué te quita tiempo hoy]
SOLUCIÓN:   [qué harías que se haga solo]
RESULTADO:  [qué documento/registro/aviso querés al final]
```

Ejemplos: contabilidad (facturas), atención al cliente (tickets), marketing (reportes de campaña), RR.HH. (onboarding), ventas (seguimiento de leads).

### Paso 2: Diagrama el flujo en una hoja

Antes de tocar Make, dibuja cajas y flechas respondiendo:

- ¿Cuál es el **trigger**? (¿evento o programado?)
- ¿Qué **módulos intermedios** necesito? (¿IA? ¿Parse JSON? ¿plantilla?)
- ¿Qué hace la **IA** en cada paso?
- ¿Cuál es el **output final** y a quién va?

✓ **Verificación:** Tienes un diagrama claro del flujo de principio a fin.

### Paso 3: Construye la v1 mínima

Arma el flujo en Make. **Tip:** parte de tus escenarios del caso de facturas — duplícalos (Export/Import Blueprint) y adáptalos en vez de empezar de cero.

- Reapunta los módulos a tu Sheet / plantilla.
- Ajusta el prompt de Gemini a tu contexto y campos.
- Que funcione **punta a punta**, aunque sea básico.

✓ **Verificación:** El flujo corre de inicio a fin (aunque falten detalles).

### Paso 4: Prueba con tus datos reales

Ejecuta con datos verídicos de tu trabajo, no de juguete. Observa:
- ¿La IA extrae bien tus campos?
- ¿El documento/registro final tiene sentido?

### Paso 5: Refina e itera

Ajusta prompts, filtros y mapeos hasta que el resultado sea usable. Si algo falla, usa **Run this module only** y revisa el History.

✓ **Verificación:** Tu flujo v1 corre con datos reales y produce un resultado que usarías.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué fue lo más difícil de adaptar el método a tu caso?**
2. **¿Qué vas a mostrar en los 5 minutos de demo de la Sesión 8?**

---

## Logros Adicionales (Opcional)

### 🟢 Suma un destinatario real
Configura que el resultado llegue a tu jefe, cliente o equipo — que sea útil para alguien más, no solo para ti.

### 🟡 Hazlo robusto
Agrega un filtro y un error handler a tu flujo propio (lo que aprendiste en la Sesión 6).

### 🔴 Documenta tu arquitectura
Escribe en media página el diagrama final + decisiones, para poder retomarlo en un mes.

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] Tu caso definido (problema → solución → resultado)
- [ ] Un diagrama del flujo
- [ ] Una v1 corriendo en Make con tus datos reales

> 📸 Ten a la mano tu flujo propio corriendo y el resultado generado con tus datos — lo presentarás en Demo Day.

---

> 📎 Si necesitas ideas de cómo estructurar prompts y campos según tu industria, mira el apéndice [`scenarios.md`](scenarios.md).
