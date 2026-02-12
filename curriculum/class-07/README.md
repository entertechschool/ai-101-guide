> 📦 **Módulo 2:** Clase 3 de 4

# Clase 07: Mi Agente Real

## Resumen

En las Clases 05 y 06 construiste un agente completo para PetShop Express: formulario, webhook, cerebro con OpenRouter, Router con 3 rutas, Gmail diferenciado y Google Sheets como bitácora. Fue tu entrenamiento. Hoy es diferente: **construyes para TU trabajo real.**

Mismas herramientas. Mismo patrón. Diferente caso: **el tuyo.** Transferencia es la prueba real de aprendizaje — no es lo mismo seguir un tutorial que aplicar lo aprendido a un contexto nuevo. Si puedes tomar la arquitectura de PetShop y adaptarla a tu caso real, dominas el concepto.

---

## ¿Por qué te sirve?

| Seguir tutorial | Aplicar a tu caso |
|----------------|-------------------|
| Copias paso a paso | Diseñas tus propias reglas |
| Funciona con datos de ejemplo | Funciona con TUS datos reales |
| Demuestras que sigues instrucciones | Demuestras que **sabes construir** |
| No sabes qué hacer si algo cambia | Sabes adaptar a cualquier contexto |

> "Saber replicar un tutorial no es lo mismo que saber construir para TU trabajo."

---

## Insight: "La arquitectura se queda. El cerebro cambia."

```
PetShop Express (C06):          Tu Caso (C07):
┌────────────────────┐          ┌────────────────────┐
│ URGENTE            │          │ [TU CATEGORÍA 1]   │
│ CONSULTA           │          │ [TU CATEGORÍA 2]   │
│ VENTA              │          │ [TU CATEGORÍA 3]   │
└────────────────────┘          └────────────────────┘

Lo que CAMBIA:                  Lo que SE QUEDA:
• SystemPrompt completo         • Webhook → OpenRouter → Router
• Categorías y reglas           • Router → Gmail ×3
• Formulario y campos           • Google Sheets (logging)
• Emails (asuntos, emojis)      • Arquitectura completa
```

---

## ¿Qué haremos en clase?

1. **Diseñar tu caso real** — Elegir proceso, definir categorías, reglas y acciones
2. **Construir tu agente** — Clonar escenario C06 y adaptar cada módulo
3. **Probar con mensajes reales** — Enviar datos reales, comparar esperado vs real, iterar

---

## Objetivos de aprendizaje

1. Diseñar un caso de triage/clasificación basado en tu trabajo real
2. Construir un agente funcional clonando y adaptando el escenario de C06
3. Iterar el SystemPrompt con datos reales hasta mejorar la precisión

---

## Preparación para la clase

### Obligatorio

1. **Escenario de C06 funcionando** — 5+ módulos en Make (Webhook → OpenRouter → Router → Gmail ×3 + Sheets)
2. **Identificar 1 proceso manual** que involucre clasificación, triage o routing en tu trabajo
3. **5 mensajes/inputs REALES** de ese proceso (escritos, copiados de email, chat, etc.)
4. **Claude abierto** — lo usarás como socio pensante para diseñar tu SystemPrompt (callback C03)

### Reflexiona antes de clase

- ¿Qué proceso repites más de 5 veces por semana que involucra decidir, clasificar o priorizar?
- ¿Podrías dividir esos mensajes/inputs en 3 categorías claras?

---

## Glosario de nuevos términos

- **Transferencia**: Aplicar un patrón aprendido (PetShop) a un contexto nuevo (tu trabajo)
- **Caso de uso**: Proceso real de tu trabajo que el agente va a resolver
- **Iteración**: Ciclo de probar → encontrar errores → mejorar SystemPrompt → re-probar
- **Arquetipos**: Patrones comunes de casos de triage por industria
- **Clonación de escenario**: Duplicar un escenario en Make como base para uno nuevo

---

## Herramientas necesarias

- [ ] 💻 Laptop con Make abierto (escenario C06 funcionando)
- [ ] 🧠 Claude abierto (socio pensante para diseñar SystemPrompt)
- [ ] 📝 5 mensajes/inputs reales de tu proceso
- [ ] 📋 Idea de tu caso de clasificación/triage
