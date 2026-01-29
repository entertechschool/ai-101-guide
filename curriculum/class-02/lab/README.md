# Lab 02: Mi Sistema de Triage con IA

Construirás un sistema de triage de mensajes de clientes que evoluciona en 4 fases. Cada fase agrega UNA técnica, y verás cómo mejora el resultado. Al terminar, tendrás un prompt maestro que combina Rol + Formato + Few-shot.

> ⏱️ **Tiempo total:** 60 minutos

### 🎯 Objetivo

Crear un prompt de triage que clasifica mensajes de clientes con prioridad, categoría y acción siguiente — y entender POR QUÉ cada técnica mejora el resultado.

---

## El Caso: PetShop Express

Trabajas en **PetShop Express**, una tienda online de productos para mascotas. Recibes mensajes de clientes por WhatsApp, email y chat. Tu reto: clasificarlos rápidamente para que el equipo sepa qué atender primero.

### Los 5 Mensajes para Clasificar

```
MENSAJE 1:
"Hola, pedí comida especial para mi perro hace 5 días y no ha llegado.
Mi perro tiene problemas renales y SOLO puede comer esta marca. Ya se
me está acabando la que tengo. ¿Pueden decirme qué pasó con mi pedido?
Número de orden: #45892"

MENSAJE 2:
"Vi en su Instagram un rascador para gatos que se ve muy bonito.
¿Todavía lo tienen? ¿Cuánto cuesta? Mi gato destruyó el anterior jaja"

MENSAJE 3:
"PÉSIMO SERVICIO. Me llegó el producto equivocado y nadie me contesta.
Llevo 3 días esperando respuesta. Quiero mi reembolso YA o voy a poner
queja en redes sociales."

MENSAJE 4:
"Buenas tardes. Necesito que corrijan mi factura porque pusieron mal
el RFC de mi empresa. No es urgente, pero sí necesito tenerla antes
del viernes para cerrar mes. Gracias."

MENSAJE 5:
"Compré unas vitaminas para mi perro y no le funcionaron. Sigue igual
de decaído. No sé si pedir reembolso, cambio por otra marca, o si
ustedes me pueden recomendar algo mejor."
```

---

## Antes de Empezar

| Requisito | Verificación |
|-----------|--------------|
| Claude abierto | Tab lista para prompts |
| Los 5 mensajes | Copiados arriba ☝️ |
| Google Doc | Para documentar tu evolución |

---

## Parte 1: El Caos — Sin Técnicas (10 min)

Empezamos con el prompt más básico posible para ver qué pasa.

### 1.1 Prompt inicial

Copia y pega en Claude:

```
Clasifica estos mensajes de clientes:

[PEGA LOS 5 MENSAJES]
```

### 1.2 Observa el resultado

Anota en tu Google Doc:
- ¿El formato es consistente entre mensajes?
- ¿Las categorías son claras o ambiguas?
- ¿Sabrías qué hacer con cada mensaje basándote en la clasificación?

### 1.3 El problema

Sin estructura, cada mensaje se clasifica diferente. No hay formato estándar. Las prioridades son subjetivas.

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

- ¿Mejoró la consistencia?
- ¿Las prioridades tienen más sentido?
- ¿Sigue habiendo problemas de formato?

### 2.3 El avance y la limitación

El rol mejora el CRITERIO de clasificación, pero el formato sigue siendo inconsistente. La IA "sabe más" pero no presenta la info de forma útil.

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

- ¿Ahora puedes comparar mensajes fácilmente?
- ¿Los campos son útiles para tomar decisión?
- ¿Hay consistencia en el formato?

### 3.3 El avance

El formato estructurado hace la clasificación ACCIONABLE. Ya no es texto libre — es una tabla que puedes usar para asignar trabajo.

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

- ¿Los ejemplos "calibraron" mejor la prioridad?
- ¿Las acciones siguientes son más específicas?
- ¿El formato se mantuvo exactamente igual?

### 4.3 El avance final

Los ejemplos enseñan el CRITERIO específico. La IA ahora entiende no solo el formato, sino el RAZONAMIENTO detrás de cada clasificación.

✅ **Checkpoint:** Clasificación final con las 3 técnicas combinadas.

---

## Parte 5: Análisis Crítico — Las Limitaciones (5 min)

Revisa tus 4 clasificaciones y busca estos errores:

### ⚠️ 3 Limitaciones Comunes de la IA en Triage

**1. Prioridad incorrecta por contexto faltante**
- Mensaje 4 dice "no urgente" pero tiene deadline real
- ¿La IA respetó "no urgente" o detectó el deadline?
- **Lección:** La IA puede sobre-confiar en lo que el cliente DICE vs lo que NECESITA

**2. Categoría ambigua**
- Mensaje 2: ¿Es "Venta" o "Producto"? (consulta de compra vs info de producto)
- Mensaje 5: ¿Es "Producto", "Queja", o "Venta"? (múltiples categorías posibles)
- **Lección:** Casos límite requieren juicio humano o categorías más específicas

**3. Urgencia por tono vs urgencia real**
- Mensaje 3 tiene tono urgente (mayúsculas, amenaza de redes)
- Mensaje 1 tiene urgencia REAL (perro con dieta médica)
- ¿La IA priorizó correctamente o se dejó llevar por el tono?
- **Lección:** El enojo no siempre = mayor prioridad real

### En tu Google Doc, anota:

> **Error que encontré:** [Describe 1 error de clasificación]
> **Por qué ocurrió:** [Tu hipótesis]
> **Cómo lo corregiría:** [Ajuste al prompt o proceso manual]

✅ **Checkpoint:** Análisis crítico completado con 1 error documentado.

---

## 📝 Entregable

**Google Doc con 3 secciones:**

### 1. Evolución del Prompt
Muestra las 4 versiones y cómo mejoró cada una:
- Versión 1: Sin técnicas
- Versión 2: +Rol
- Versión 3: +Formato
- Versión 4: +Few-shot (tu prompt maestro final)

### 2. Tabla de Clasificación Final
La tabla con los 5 mensajes clasificados usando tu prompt completo.

### 3. Reflexión Crítica
```
ERROR ENCONTRADO:
- Mensaje #: ___
- Error: ___
- Por qué ocurrió: ___
- Cómo lo corregiría: ___
```

**Entrega:** Link público del Google Doc.

---

## Checklist Final

- [ ] ¿Documenté las 4 versiones del prompt?
- [ ] ¿Mi tabla tiene los 5 mensajes clasificados?
- [ ] ¿Identifiqué al menos 1 error/limitación de la IA?
- [ ] ¿Expliqué cómo corregiría ese error?

---

## 🚀 Bonus: Tus Mensajes Reales (Opcional)

Si tienes acceso a mensajes reales de clientes de tu trabajo:

1. Anonimiza los datos (nombres, números de cuenta)
2. Usa tu prompt maestro para clasificar 5 mensajes reales
3. Compara: ¿Funcionó igual de bien? ¿Qué ajustes necesita?

**Tip:** Los prompts que funcionan con casos mockup a veces fallan con datos reales. Eso es normal — es parte del proceso de refinamiento.
