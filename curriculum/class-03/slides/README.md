<!-- .slide: data-background="#0A192F" -->

# SESIÓN 3
## API KEY DE GEMINI

Que la IA procese tus datos automáticamente

*Sesión 3 de 8 · 60 minutos · Online en vivo*

---

## TRANSICIÓN · LA IA ENTRA AL FLUJO

### La sesión pasada:

- Armaste tu primer escenario en Make
- Drive → Sheet, sin IA

### Hoy:

- Conectas **Gemini** dentro del escenario
- La IA lee la factura y extrae datos sola

> "Hoy tu flujo deja de solo copiar y empieza a entender."

---

## QUÉ VAMOS A LOGRAR HOY

### OBJETIVO DE LA SESIÓN

Integrar Gemini dentro de un flujo de Make generando una API key en Google AI Studio.

### FUNDAMENTOS

1. ¿Qué es una API?
2. ¿Qué es una API key?
3. Connection en Make vs API key directa
4. Modelos de Gemini — Flash vs Pro

### MINI-PROYECTO

La IA lee la factura y extrae el proveedor

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿Sabes qué es una API?

**02** ¿Te suena "clave secreta" / "API key" / "token"?

**03** ¿Por qué crees que una IA cuesta plata cada vez que la usas?

> 💡 La API es el puente entre tu flujo de Make y la IA. Hoy aprendemos a usarlo.

---

## FUNDAMENTO 1 · ¿QUÉ ES UNA API?

*Un puente entre apps*

Permite que una app le pida algo a otra de forma estructurada:

- **MAKE** — tu flujo
- **API GEMINI** — el puente
- **RESPUESTA** — lo que devuelve la IA

> Tu escenario "llama" a Gemini y recibe el resultado.

---

## FUNDAMENTO 2 · ¿QUÉ ES UNA API KEY?

*Una llave personal y secreta*

- 🔑 **Personal** — te identifica como usuario
- 🔒 **Secreta** — no compartir, no subir a GitHub
- 💵 **Asociada a una cuenta** (free tier de Gemini)
- 📍 Se genera en **Google AI Studio** (aistudio.google.com)

---

## EJEMPLO REAL · PANTALLA DE AI STUDIO

*Donde generas y copias tu key*

```
GOOGLE AI STUDIO · API Keys
──────────────────────────────────
[ + Create API Key ]

Curso IA — Make Gemini
AIzaSyD-XXXXXXXXXXXXXXXX...   [👁 Show] [📋 Copy]

⚠ No la compartas. No la subas a GitHub.
```

---

## FUNDAMENTO 3 · CONNECTION VS API KEY DIRECTA

*Make guarda credenciales en "Connections"*

| CONNECTION DE MAKE | API KEY MANUAL |
|--------------------|----------------|
| Se configura 1 vez | Se pega en cada módulo |
| Se reutiliza en cualquier escenario | Riesgo de exponerla |
| Más segura | Solo casos puntuales |

---

## FUNDAMENTO 4 · GEMINI FLASH VS PRO

*Distintos modelos, distintos usos*

| GEMINI 2.5 FLASH | GEMINI 2.5 PRO |
|------------------|----------------|
| Rápido | Más capaz |
| Económico | Más caro |
| Tareas simples, alto volumen | Análisis profundo |

> Para leer facturas: **Flash** alcanza y sobra.

---

## MINI-PROYECTO · LA IA EXTRAE EL PROVEEDOR

*Sumamos Gemini al escenario de la sesión 2*

**Individual**

### QUÉ HACER

1. Generar API key en Google AI Studio (guardarla segura)
2. Crear **Connection** a Gemini en Make con esa key
3. Agregar el módulo **Gemini** tras el trigger de Drive
4. Pedirle: "extrae el nombre del proveedor de esta factura"
5. Mapear la respuesta a una columna **"Proveedor"** del Sheet

✓ **Verificación:** Subir factura → Gemini lee → Sheet con proveedor lleno

---

## LO QUE TE LLEVAS HOY

**01** API key generada y guardada en Make como Connection

**02** Gemini integrado al escenario procesando facturas

**03** Una columna del Sheet llenándose sola con la IA

### PRÓXIMA SESIÓN

Sesión 4: JSON + Parse JSON. Haremos que la IA devuelva varios datos juntos, ordenados.
