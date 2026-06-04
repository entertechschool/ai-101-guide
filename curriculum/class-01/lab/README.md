# Lab 01: 3 prompts profesionales

## 🎯 Objetivo

Construir **3 prompts profesionales** que resuelven tareas reales de tu trabajo, aplicando la estructura **Rol + Tarea + Contexto + Formato**.

---

## 🔑 Conceptos Clave

- **Prompt profesional** — Instrucción con 4 elementos: Rol + Tarea + Contexto + Formato.
- **Output libre vs estructurado** — Texto para leer, o JSON para que lo procese otra app.

---

## ⚙️ Setup Inicial

Esta es la primera sesión del curso. Verifica que tengas todo listo:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Cuenta de Gemini activa | Abre [gemini.google.com](https://gemini.google.com/){:target="_blank"} y envía un mensaje de prueba |
| ☐ | 3 tareas reales en mente | Tareas de tu trabajo que te quitan tiempo (correos, reuniones, respuestas a clientes) |

---

## Mini-proyecto: 3 prompts profesionales

> Trabajarás los 3 prompts en vivo. Cada uno aplica la misma anatomía: **Rol + Tarea + Contexto + Formato**.

### Paso 1: Elige tus 3 tareas reales

Piensa en 3 tareas que haces seguido y te consumen tiempo. Usaremos estas 3 como guía, pero adáptalas a tu trabajo:

- Clasificar un correo de cliente
- Resumir una reunión
- Redactar una respuesta de venta

### Paso 2: Prompt 1 — Clasificar un correo

Aplica la anatomía completa. Usa esta base y reemplaza los bloques marcados:

```
Actúa como [<!-- tu rol: asesor comercial, soporte, etc. -->].
Clasifica el siguiente correo en una de estas categorías:
[<!-- tus categorías: Venta nueva / Queja / Consulta / Spam -->].
Contexto: [<!-- dato relevante: cliente VIP, factura impaga, etc. -->].
Devuelve la categoría en 1 palabra y una explicación de máximo 2 líneas.

Correo:
[<!-- pega aquí un correo real -->]
```

✓ **Verificación:** Gemini devuelve la categoría en 1 palabra + explicación breve.

### Paso 3: Prompt 2 — Resumir una reunión

```
Actúa como [<!-- tu rol -->].
Resume la siguiente reunión en un resumen ejecutivo.
Formato: 4-5 bullets + una lista de "Acciones siguientes" con responsable.

Notas de la reunión:
[<!-- pega notas o la transcripción -->]
```

✓ **Verificación:** El resumen tiene bullets + acciones siguientes claras.

### Paso 4: Prompt 3 — Redactar respuesta de venta

```
Actúa como [<!-- tu rol comercial -->].
Redacta una respuesta para este cliente.
Contexto: [<!-- situación: cotización pendiente, seguimiento, objeción de precio -->].
Formato: tono profesional y cercano. Dame 2 opciones de respuesta.

Mensaje del cliente:
[<!-- pega el mensaje -->]
```

✓ **Verificación:** Recibes 2 opciones de respuesta listas para enviar.

### Paso 5: Prueba y ajusta

Itera cada prompt hasta que el resultado esté listo para usar sin retoques. Pregúntate:

- ¿Qué elemento tuvo más impacto: el contexto, el formato o la tarea?
- ¿Le falta algún dato a la IA para acertar?

✓ **Verificación:** Los 3 prompts producen resultados que usarías tal cual.

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Cuál de los 4 elementos (rol, tarea, contexto, formato) cambió más el resultado?**
2. **¿Qué tarea de tu trabajo vas a empezar a resolver con prompts esta semana?**

---

## Logros Adicionales (Opcional)

### 🟢 Pide el resultado en JSON
Repite el Prompt 1 pidiendo la salida como JSON (`categoria`, `urgencia`, `accion`). Observa la diferencia con el texto libre — eso es lo que la Sesión 4 hará viajar dentro de un flujo.

### 🟡 Arma tu mini-biblioteca de prompts
Guarda los 3 prompts en un Google Doc. Súmale 2 más para otras tareas recurrentes de tu trabajo.

### 🔴 Prueba un caso límite
Dale al Prompt 1 un correo ambiguo y observa si la IA acierta o se confunde. ¿Qué contexto le faltó?

---

## 📝 Cierre de la sesión

Esta práctica se valida **en clase** (0 = no la hiciste / 100 = la hiciste). No hay entrega posterior.

### Lo que debes mostrar

- [ ] Los 3 prompts escritos con la anatomía Rol + Tarea + Contexto + Formato
- [ ] Cada prompt ejecutado en Gemini con un resultado usable

> 📸 Ten a la mano la pantalla de Gemini con uno de tus prompts y su respuesta, por si el facilitador pide mostrarlo.
