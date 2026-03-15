# Lab 02: Mi Sistema de Triage — Diseño de instrucciones efectivas

Construirás un sistema de triage que evoluciona en 4 fases. Cada fase agrega UNA técnica y verás cómo mejora el resultado.

> ⏱️ **Tiempo total:** 65 minutos

---

## El Caso: PetShop Express

Trabajas en **PetShop Express**, una tienda online de productos para mascotas. Recibes mensajes de clientes por WhatsApp, email y chat. Tu reto: clasificarlos rápidamente para que el equipo sepa qué atender primero.

### Los 5 Mensajes para Clasificar

```
MENSAJE 1: "Hola, pedí comida especial para mi perro hace 5 días y no ha llegado. Mi perro tiene problemas renales y SOLO puede comer esta marca. Ya se me está acabando. Orden: #45892"

MENSAJE 2: "Vi en su Instagram un rascador para gatos que se ve muy bonito. ¿Todavía lo tienen? ¿Cuánto cuesta? Mi gato destruyó el anterior jaja"

MENSAJE 3: "PÉSIMO SERVICIO. Me llegó el producto equivocado y nadie me contesta. Llevo 3 días esperando. Quiero mi reembolso YA o voy a poner queja en redes."

MENSAJE 4: "Necesito que corrijan mi factura porque pusieron mal el RFC de mi empresa. No es urgente, pero sí necesito tenerla antes del viernes para cerrar mes."

MENSAJE 5: "Compré unas vitaminas para mi perro y no le funcionaron. Sigue igual de decaído. No sé si pedir reembolso, cambio por otra marca, o si me pueden recomendar algo."
```

---

## Parte 1: El Caos — Sin Técnicas (10 min)

Empezamos con el prompt más básico posible para ver qué pasa.

### 1.1 Prompt inicial

Copia y pega en Claude:

```
Clasifica estos mensajes de clientes:

[PEGA LOS 5 MENSAJES]
```

### 1.2 Observa y documenta

Anota en tu Google Doc: ¿El formato es consistente? ¿Las categorías son claras? ¿Sabrías qué hacer con cada mensaje?

✅ **Checkpoint:** Tienes tu primera clasificación caótica documentada.

---

## Parte 2: +Rol — El Experto (15 min)

Agregamos UN elemento: el rol de experto.

### 2.1 Prompt con rol

```
Eres un agente de soporte al cliente senior con 5 años de experiencia
en e-commerce de productos para mascotas. Conoces los tipos de
problemas más comunes y sabes priorizar según impacto en el cliente.

Clasifica estos mensajes de clientes:

[PEGA LOS 5 MENSAJES]
```

### 2.2 Compara con Parte 1

¿Mejoró la consistencia? ¿Las prioridades tienen más sentido? El rol mejora el CRITERIO pero el formato sigue inconsistente.

✅ **Checkpoint:** Segunda clasificación con rol, comparación documentada.

---

## Parte 3: +Formato Estructurado (15 min)

Agregamos formato de tabla con campos específicos.

### 3.1 Prompt con rol + formato

```
Eres un agente de soporte al cliente senior con 5 años de experiencia
en e-commerce de productos para mascotas.

Clasifica estos mensajes en una tabla con las siguientes columnas:

| # | Prioridad | Categoría | Resumen (1 línea) | Acción siguiente | Tiempo máx |
|---|-----------|-----------|-------------------|------------------|------------|

Usa estos códigos de prioridad:
- 🔴 Alta: Requiere acción inmediata (cliente en riesgo, escalamiento)
- 🟡 Media: Importante pero no urgente (puede esperar horas)
- 🟢 Baja: Consulta general (puede esperar 24h)

Categorías permitidas: Envío, Producto, Facturación, Venta, Queja

Mensajes a clasificar:

[PEGA LOS 5 MENSAJES]
```

### 3.2 Compara con Parte 2

¿Puedes comparar mensajes fácilmente? El formato estructurado hace la clasificación ACCIONABLE.

✅ **Checkpoint:** Tercera clasificación en tabla, campos consistentes.

---

## Parte 4: +Few-shot — Los Ejemplos (15 min)

Agregamos 2 ejemplos que muestran EXACTAMENTE cómo clasificar.

### 4.1 Prompt completo con Few-shot

```
Eres un agente de soporte al cliente senior con 5 años de experiencia
en e-commerce de productos para mascotas.

Clasifica mensajes de clientes en una tabla con estas columnas:

| # | Prioridad | Categoría | Resumen (1 línea) | Acción siguiente | Tiempo máx |
|---|-----------|-----------|-------------------|------------------|------------|

Prioridades:
- 🔴 Alta: Acción inmediata (cliente en riesgo, escalamiento)
- 🟡 Media: Importante pero no urgente (horas)
- 🟢 Baja: Consulta general (24h)

Categorías: Envío, Producto, Facturación, Venta, Queja

### EJEMPLOS DE CLASIFICACIÓN CORRECTA:

Mensaje: "Mi pedido llegó roto y necesito el producto para mañana porque
es regalo de cumpleaños de mi hija"
| 1 | 🔴 Alta | Envío | Producto dañado, urgencia por evento | Reenvío express + cupón disculpa | 2h |

Mensaje: "¿Tienen descuento por volumen? Quiero comprar 10 bolsas de
alimento para mi refugio"
| 2 | 🟢 Baja | Venta | Consulta de precio mayoreo para refugio | Responder con política de descuentos | 24h |

### AHORA CLASIFICA ESTOS MENSAJES:

[PEGA LOS 5 MENSAJES]
```

### 4.2 Compara con Parte 3

¿Los ejemplos "calibraron" mejor las prioridades? Los ejemplos enseñan el CRITERIO — la IA entiende el RAZONAMIENTO, no solo el formato.

✅ **Checkpoint:** Clasificación final con las 3 técnicas combinadas.

---

## Parte 5: Análisis Crítico — ¿Dónde Falló? (10 min)

La IA no es perfecta. Vamos a encontrar sus errores.

### 5.1 Encuentra UN error

Enfócate en tu Versión 4 (Few-shot). Busca un mensaje donde la IA se equivocó:

- **Mensaje 1 vs 3:** ¿Priorizó la urgencia REAL (salud del animal) o el TONO (mayúsculas, amenaza)?
- **Mensaje 4:** Dice "no es urgente" pero tiene deadline real. ¿La IA lo detectó?
- **Mensaje 5:** ¿La categoría elegida es la más útil para actuar?

### 5.2 Documenta el error

```
ERROR ENCONTRADO:
- Mensaje #: ___
- Qué hizo la IA: ___
- Qué debería haber hecho: ___
- Cómo ajustaría el prompt: ___
```

✅ **Checkpoint:** Tienes 1 error documentado con propuesta de corrección.

---

## 📝 Entregable

**Google Doc con 3 prompts documentados (link público):**

1. **Prompt de triage** — RICE + Few-shot + tabla clasificada
2. **Prompt para TU trabajo** — RICE aplicado a tarea real con resultado
3. **Reflexión crítica** — 1 error encontrado + corrección propuesta

---

## Checklist Final

- [ ] ¿Documenté el prompt de triage con RICE + Few-shot?
- [ ] ¿Creé un segundo prompt aplicado a MI trabajo?
- [ ] ¿Identifiqué al menos 1 error/limitación de la IA?

---

## Bonus: Tus Mensajes Reales (Opcional)
Si tienes mensajes reales de clientes: anonimiza datos, usa tu prompt maestro, y compara. Los prompts que funcionan con mockups a veces fallan con datos reales — ajustar es parte del proceso.
