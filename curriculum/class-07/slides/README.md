<!-- .slide: data-background="#0A192F" -->

# Clase 07: Mi Agente Real
## De tutorial a tu caso de trabajo

*AI 101 - Entertech School*

---

## 🔗 Transición: C05 → C06 → C07

### El arco de M2:

| Clase | Qué hiciste | Patrón |
|-------|-------------|--------|
| **C05** | Construiste el cerebro (Form → Webhook → OpenRouter) | Seguir instrucciones |
| **C06** | Completaste el agente (Router + Gmail + Sheets) | Expandir con guía |
| **C07** | Construyes para TU trabajo | **Aplicar por tu cuenta** |

> "PetShop fue el entrenamiento. Ahora es real."

---

## 🧠 Pregunta Detonadora

### Tu jefe dice: "Hazme un agente para nuestro equipo." ¿Qué es lo PRIMERO que haces?

**A)** Copiar el escenario de PetShop y cambiar los nombres

**B)** Definir las categorías y reglas de MI caso antes de tocar Make

**C)** Buscar un tutorial nuevo en YouTube

**D)** Pedirle a ChatGPT que lo haga

> 🕐 30 segundos para pensar → levanten la mano

---

## 🧠 Pregunta Detonadora — Respuesta

**Respuesta correcta: B**

- **A:** ❌ Si copias PetShop tal cual, tienes un agente de mascotas. Inútil para tu equipo
- **B:** ✅ PRIMERO defines TU caso. DESPUÉS adaptas la arquitectura
- **C:** ❌ No necesitas tutorial nuevo — ya tienes el patrón
- **D:** ❌ Sin tu contexto, cualquier IA genera algo genérico

> **Antes de tocar Make, define TU caso:** categorías, reglas, acciones.

---

## 🎬 Demo: Agente del Facilitador

### No es PetShop. Es un caso REAL diferente.

El facilitador muestra su propio agente:

1. Envía un mensaje desde su formulario
2. OpenRouter clasifica con sus categorías
3. Router toma la ruta correcta
4. Gmail envía email con emoji apropiado
5. Google Sheets registra la decisión

> "Mismo patrón, caso diferente. Eso es **transferencia**."

---

## 6 Arquetipos por Industria

| Industria | Caso | Categorías |
|-----------|------|------------|
| Freelancer | Triage solicitudes | PROYECTO / CONSULTA / SPAM |
| Ventas | Clasificar leads | CALIENTE / TIBIO / FRÍO |
| Soporte | Priorizar tickets | URGENTE / NORMAL / FAQ |
| RRHH | Filtrar candidatos | AVANZAR / REVISAR / RECHAZAR |
| Marketing | Clasificar feedback | POSITIVO / MEJORA / QUEJA |
| Educación | Triage consultas | ACADÉMICO / TÉCNICO / ADMIN |

> 💡 "¿Qué haces más de 5 veces por semana que involucre decidir o clasificar?"

---

## De PetShop a TU Caso

```
 Lo que CAMBIA:              Lo que SE QUEDA:
┌───────────────────┐       ┌───────────────────────────────┐
│ • SystemPrompt    │       │ • Webhook → OpenRouter        │
│ • Categorías      │       │ • Router → 3 rutas Gmail      │
│ • Formulario      │       │ • Google Sheets (logging)     │
│ • Emails (asunto) │       │ • Arquitectura completa       │
└───────────────────┘       └───────────────────────────────┘
```

### La arquitectura se queda. El cerebro cambia.

Clonas el escenario → cambias SystemPrompt + categorías + form → tienes un agente nuevo.

---

## ⚠️ Anti-Hype

### Tu agente también va a fallar.

- Mismos errores de PetShop, nuevo contexto
- El SystemPrompt necesita iteración con datos reales
- 3 de 5 mensajes bien en el primer intento = normal
- La habilidad no es que funcione perfecto — es saber **CÓMO corregirlo**

> "Un agente para TU caso vale 10x más que uno perfecto de tutorial."

---

## Lab Time

### Mi Agente Real — 90 min

| Parte | Tiempo | Qué haces |
|-------|--------|-----------|
| **1. Diseñar** | 20 min | Elegir caso + definir categorías + SystemPrompt con Claude |
| **2. Construir** | 50 min | Clonar escenario + form nuevo + adaptar módulos |
| **3. Probar** | 20 min | 5 mensajes reales + tabla resultados + iterar |

> 💡 Tu experiencia de C02 + C03 + C05 + C06 = todo lo que necesitas.

---

## ✅ Checkpoints

### Parte 1:
- [ ] Caso elegido con 3 categorías + reglas
- [ ] SystemPrompt escrito con ayuda de Claude

### Parte 2:
- [ ] Escenario clonado en Make
- [ ] Form v0 nuevo deployado
- [ ] Módulos adaptados (OpenRouter + Router + Gmail + Sheets)

### Parte 3:
- [ ] 5 mensajes reales enviados
- [ ] Tabla esperado vs real completada
- [ ] Al menos 1 mejora al SystemPrompt documentada

---

## 📝 Entrega + Preview C08

### Tu entregable (Google Doc, nueva sección):
1. Mi caso real + categorías + reglas
2. Screenshot Make (escenario adaptado) + SystemPrompt
3. URL del formulario nuevo
4. Tabla de resultados (esperado vs real)
5. Mejora documentada

### Próxima clase: Demo Day

> **Presentas TU agente EN VIVO.**
> No slides. No documento. Tu agente funcionando.
> 5 minutos. Alguien del público envía un mensaje.

---

## 💡 Reflexión

### Hoy aprendiste:
- A transferir un patrón aprendido a tu contexto real
- Que diseñar el caso importa MÁS que la herramienta
- Que iterar con datos reales es lo que hace funcionar un agente
- Que la arquitectura es reutilizable — el cerebro es lo que personalizas

### La pregunta:
> "¿Podrías hacer esto para OTRO proceso de tu trabajo? Porque ya tienes el patrón."
