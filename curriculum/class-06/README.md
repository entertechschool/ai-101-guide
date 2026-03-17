> 📦 **Módulo 2:** Clase 2 de 4

# Clase 06: Tu Agente Inteligente

## Resumen

En Clase 05 construiste el cerebro de un agente: recibe datos desde un formulario, la IA clasifica con OpenRouter. Hoy lo completas y lo haces inteligente: envía emails diferenciados (Gmail), toma rutas diferentes según la categoría (Router) y registra cada decisión en una hoja (Google Sheets).

La diferencia entre un flujo lineal y un agente inteligente: un flujo lineal hace lo mismo siempre — todos los mensajes siguen el mismo camino. Un agente inteligente **DECIDE** qué camino tomar y **REGISTRA** lo que hizo. Hoy tu agente pasa de "tubería" a "árbol de decisiones".

```
                                    ┌─ 🔴 URGENTE → Gmail rojo
Form → Webhook → OpenRouter → Router├─ 🔵 CONSULTA → Gmail normal
                                    └─ 🟢 VENTA → Gmail + Sheets
```

---

## ¿Por qué te sirve?

### Flujo lineal vs agente inteligente

| Flujo lineal (C05) | Agente inteligente (C06) |
|---------------------|--------------------------|
| Todos los mensajes → mismo camino | Cada mensaje → ruta diferente |
| Un solo tipo de respuesta | Respuesta adaptada a la categoría |
| Sin registro de decisiones | Cada decisión queda en Google Sheets |
| "Tubería" — entra y sale igual | "Árbol" — entra y se ramifica |

### Lo que ganas

- **Acción diferenciada**: Un mensaje urgente no recibe el mismo email que una consulta
- **Trazabilidad**: Google Sheets registra cada decisión — puedes auditar tu agente
- **Escalabilidad**: Agregar una nueva categoría = agregar una nueva ruta

---

## ¿Qué haremos en clase?

1. **Completarás tu agente** — Agregar Gmail para que el agente envíe emails con la clasificación (momento WOW)
2. **Lo harás inteligente** — Router con 3 rutas (URGENTE, CONSULTA, VENTA) + Google Sheets como registro
3. **Competirás con tus compañeros** — Battle: ¿quién clasifica mejor los 5 mensajes de PetShop Express?
4. **Analizarás los resultados** — Documentar fallas, comparar con C02, reflexionar

## 🎯 Objetivos de aprendizaje

Al finalizar esta clase, serás capaz de:

1. **Completar un agente end-to-end** — Desde el formulario hasta el email con clasificación
2. **Expandir un agente con lógica condicional y logging** — Router para branching + Google Sheets para registro
3. **Evaluar calidad de clasificación y competir con pares** — Analizar resultados y votar el mejor SystemPrompt

---

## 📌 Preparación para la clase

> **Antes de llegar a clase, prepárate:**

### ✅ Tareas previas (OBLIGATORIAS)

1. **Tener tu escenario de C05 funcionando en Make**
   - Webhook → OpenRouter (2 módulos)
   - Si no lo terminaste, el facilitador te ayudará al inicio

2. **Tener una hoja de Google Sheets nueva**
   - Crear una hoja vacía (la configuraremos en clase)
   - Nombre sugerido: "Agente Triage - Log"

3. **Tener tu SystemPrompt de C05 a la mano**
   - Lo usarás como base y lo mejorarás durante el battle

### 🧠 Reflexiona sobre esto

- ¿Qué procesos de tu trabajo tienen diferentes caminos según el tipo de entrada?
- ¿Alguna vez necesitaste un registro de decisiones tomadas por otros (o por ti)?

---

## Glosario de nuevos términos

- **Router**: Módulo de Make que permite crear múltiples rutas de salida desde un punto
- **Filter**: Condición que determina cuándo se activa una ruta del Router (ej: "output contains URGENTE")
- **Branching**: Patrón donde un flujo se divide en múltiples caminos según condiciones
- **Logging**: Registrar cada acción/decisión del agente en un lugar persistente (Google Sheets)
- **Google Sheets (en Make)**: Módulo que permite agregar filas a una hoja de cálculo automáticamente

---

## La Evolución del Agente

```
C05: El agente PIENSA
   Form → Webhook → OpenRouter (clasifica)
   → Ve resultado en Make History

         ↓ HOY ↓

C06: El agente PIENSA + ACTÚA + DECIDE DIFERENTE + REGISTRA
   Form → Webhook → OpenRouter → Router → [3 rutas Gmail] + Sheets
   → Emails diferenciados + log de decisiones
```

---

## Recursos Adicionales

- [Make Router Module](https://www.make.com/en/help/modules/router){:target="_blank"} - Documentación oficial del Router
- [Google Sheets en Make](https://www.make.com/en/help/app/google-sheets){:target="_blank"} - Integración con Google Sheets

---

## Herramientas necesarias

- [ ] 💻 Laptop con Make abierto (escenario de C05)
- [ ] 📊 Google Sheets nueva y vacía
- [ ] 📝 SystemPrompt de C05 (en tu Google Doc)
- [ ] 🔗 URL de tu formulario v0 (de C05)
