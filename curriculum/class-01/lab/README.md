# Lab 01: Prompts y Gems

## 🎯 Objetivos

1. Diseñar 3 variaciones del mismo prompt aplicando la estructura Rol + Contexto + Tarea + Formato + Restricciones.
2. Escribir el brief de tu proyecto de instrucción (1 párrafo) usando la plantilla de 4 elementos.
3. Configurar un Gem personalizado con instrucciones, brief y al menos 1 archivo de referencia.

---

## 🔑 Conceptos Clave

- **Prompt profesional** — Instrucción con 5 elementos: Rol + Contexto + Tarea + Formato + Restricciones.
- **Brief del proyecto de instrucción** — Resumen de 1 párrafo del reporte que vas a automatizar durante el curso.
- **Gem** — Asistente personalizado de Gemini con instrucciones y archivos fijos.

---

## ⚙️ Setup Inicial

Esta es la primera sesión del curso. Verifica que tengas todo listo:

| ✓ | Requisito | Verificación |
|---|-----------|--------------|
| ☐ | Cuenta de Gemini activa | Abre [gemini.google.com](https://gemini.google.com/){:target="_blank"} y envía un mensaje de prueba |
| ☐ | Google Drive con carpeta "Proyecto de Instrucción" | Crea una carpeta nueva en Drive para guardar tus entregables |
| ☐ | 1 archivo real de tu trabajo | Un reporte, plantilla o ejemplo que describa el resultado que buscas (PDF, Doc, captura) |

> ⚠️ Si no tienes un archivo de referencia listo, usa un documento similar de cualquier otra empresa o un ejemplo genérico. Puedes reemplazarlo después.

---

## Actividad 1: Diseña tu primer prompt profesional (35 min)

### 1.1 Recibe el prompt genérico

El prompt base que vas a mejorar es:

```
Escribe sobre productividad
```

Ese prompt es genérico — Gemini responderá algo útil pero que sirve a cualquiera. Tu trabajo es hacerlo específico para TU contexto.

### 1.2 Crea 3 variaciones progresivas

Escribe 3 variaciones del prompt. Cada una suma elementos:

**Variación 1 — Rol + Tarea:**

```
Actúa como [<!-- Tu rol profesional -->].
Escribe sobre cómo mejorar la productividad en [<!-- tu industria -->].
```

**Variación 2 — suma Contexto:**

```
Actúa como [<!-- Tu rol profesional -->].
Mi contexto es [<!-- tamaño de empresa, tipo de equipo, herramientas actuales -->].
Escribe sobre cómo mejorar la productividad en [<!-- tu industria -->].
```

**Variación 3 — suma Formato y Restricciones:**

```
Actúa como [<!-- Tu rol profesional -->].
Mi contexto es [<!-- tamaño de empresa, tipo de equipo, herramientas actuales -->].
Escribe sobre cómo mejorar la productividad en [<!-- tu industria -->].
Formato: lista numerada de 5 tips, cada uno con [<!-- máximo 40 palabras -->].
Restricciones: [<!-- evita herramientas pagas / jerga técnica / soluciones que requieran permisos adicionales -->].
```

### 1.3 Envía las 3 variaciones a Gemini

Ejecuta las 3 en Gemini (en conversaciones separadas para comparar) y observa:

- ¿Cuál respuesta es más útil para tu trabajo?
- ¿Qué elemento del prompt tuvo más impacto: contexto, formato o restricciones?

✅ **Checkpoint:** Tienes 3 conversaciones en Gemini con las 3 variaciones y puedes explicar por qué la variación 3 es más útil que la 1.

---

## Actividad 2: Define tu proyecto de instrucción (35 min)

### 2.1 Piensa en tu trabajo real

Responde mentalmente (o en un papel):

- ¿Qué reporte semanal o mensual armas hoy a mano?
- ¿Quién lo recibe (jefe, cliente, equipo)?
- ¿Qué datos incluye (números, textos, gráficos)?
- ¿Cuánto tiempo te quita (horas/semana)?

### 2.2 Escribe tu brief en 1 párrafo

Abre un Google Doc en tu carpeta "Proyecto de Instrucción" y escribe:

```
Quiero automatizar [<!-- tipo de reporte -->] que genero [<!-- frecuencia: semanal, mensual -->],
dirigido a [<!-- destinatario: jefe, cliente, equipo -->],
que incluye [<!-- tipo de datos: ventas, alcance, métricas -->],
para ahorrar [<!-- tiempo estimado: 4 horas/semana -->].
```

### 2.3 Ejemplos válidos como referencia

| Rol | Brief |
|-----|-------|
| Gerente comercial | "Quiero automatizar el reporte semanal de ventas que genero cada viernes, dirigido a mis 3 vendedores y al gerente general, que incluye ventas totales, clientes nuevos y hallazgos por vendedor, para ahorrar 4 horas semanales." |
| Freelance marketing | "Quiero automatizar el reporte mensual de desempeño de campañas, dirigido a mis clientes de marketing, que incluye alcance, engagement y recomendaciones, para ahorrar 6 horas mensuales." |
| Coordinador académico | "Quiero automatizar el reporte de progreso de cohortes que genero cada miércoles, dirigido al director académico, que incluye asistencia, entregables y alertas tempranas, para ahorrar 3 horas semanales." |

### 2.4 Comparte con el grupo

Pega tu brief en el chat del aula para recibir feedback rápido del instructor y compañeros.

✅ **Checkpoint:** Tu brief está en un Google Doc dentro de la carpeta "Proyecto de Instrucción" y contiene los 4 elementos (qué + cuándo + quién + datos + tiempo).

---

## Actividad 3: Crea tu Gem asistente del curso (40 min)

### 3.1 Entra a Gems

En Gemini, busca en el menú lateral izquierdo "**Gestor de Gems**" → "**Nuevo Gem**".

### 3.2 Configura los campos del Gem

**Nombre:**

```
Asistente de mi proyecto — [<!-- Tu nombre -->]
```

**Instrucciones del Gem:** pega la plantilla y personaliza los bloques marcados:

```
Eres mi asistente de curso. Me acompañarás durante las 8 sesiones del programa
AI 101, en las que construiré un sistema automatizado de reportes.

MI PROYECTO:
[<!-- Pega aquí el brief completo de la Actividad 2 -->]

MI ROL Y CONTEXTO:
- Rol: [<!-- Tu rol profesional -->]
- Industria: [<!-- Tu industria -->]
- Herramientas actuales: [<!-- Google Workspace, Excel, WhatsApp, etc. -->]

TU ROL:
- Ayudarme a diseñar prompts, estructuras de datos y textos del reporte.
- Recordar el contexto de mi proyecto en todo momento.
- Sugerir mejoras cuando te pregunte, con ejemplos concretos.

TONO: profesional pero cercano, directo al punto. Responde en español latinoamericano.
```

### 3.3 Sube al menos 1 archivo de referencia

Arrastra al Gem un archivo real:
- Un reporte que hayas generado manualmente antes
- Un documento con el tono de marca de tu empresa
- Un ejemplo de los datos que manejas

### 3.4 Prueba el Gem

Pídele al Gem 3 cosas:

1. `Resume mi brief en una línea.`
2. `¿Qué 6 secciones debería tener mi reporte ejecutivo?`
3. `Según el archivo que te subí, ¿qué datos ves que deberíamos capturar en el sistema?`

Verifica que el Gem responde mencionando **tu** contexto (no uno genérico).

✅ **Checkpoint:** Tu Gem responde las 3 preguntas haciendo referencia al brief y al archivo que subiste.

---

## 📁 Estructura Final del Proyecto

```
Google Drive/
└── Proyecto de Instrucción/
    ├── brief.doc              # Brief de 1 párrafo (Actividad 2)
    ├── archivo-referencia.*   # Archivo que subiste al Gem (Actividad 3)
    └── capturas/
        ├── prompt-v1.png      # Captura variación 1 (Actividad 1)
        ├── prompt-v2.png      # Captura variación 2
        └── prompt-v3.png      # Captura variación 3
```

---

## Reflexión

Antes de terminar, responde brevemente:

1. **¿Qué fue lo más útil que aprendiste hoy?**
2. **¿Cómo aplicarías la estructura de prompt profesional en tu trabajo esta semana?**
3. **¿Qué pregunta te quedó sin responder?**

---

## Logros Adicionales (Opcional)

### 🟢 Sube más archivos al Gem
Agrega 2-3 archivos adicionales (plantillas, manuales, ejemplos de tono). Observa cómo cambian las respuestas del Gem. Más contexto = mejores respuestas.

### 🟡 Diseña una biblioteca de prompts
Crea un Google Doc con 5 prompts profesionales para tareas recurrentes de tu trabajo (responder clientes, redactar correos, resumir reuniones). Usa la estructura de 5 elementos.

### 🔴 Prueba el Gem con un caso límite
Pregúntale algo que NO esté en el archivo de referencia y observa si alucina o si admite el límite. En la Clase 6 aprenderás a mejorar esto con few-shot y chain-of-thought.

---

## 📝 Entrega

### Checklist

- [ ] Brief del proyecto de instrucción (1 párrafo) en Google Doc
- [ ] Gem funcionando con nombre, instrucciones y al menos 1 archivo
- [ ] 3 capturas de pantalla de las variaciones del prompt (Actividad 1)

### Entregable

📸 **Screenshot** de tu Gem respondiendo la pregunta "Resume mi brief en una línea", donde se vea:
- El nombre del Gem visible en la parte superior
- La respuesta haciendo referencia a tu brief real
- Tu nombre o correo de Gemini visible (para autenticar el trabajo)

> ⚠️ El entregable debe mostrar tu cuenta de Gemini visible para verificar que es tu Gem.
