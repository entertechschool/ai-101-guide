# Biblioteca de Prompts — AI 101

Prompts de referencia usados durante el curso. Copia y adapta los bloques `[<!-- ... -->]` a tu caso.

---

## Índice

1. [Anatomía del prompt profesional (Sesión 01)](#1-anatomía-del-prompt-profesional-sesión-01)
2. [Clasificar un correo (Sesión 01)](#2-clasificar-un-correo-sesión-01)
3. [Resumir una reunión (Sesión 01)](#3-resumir-una-reunión-sesión-01)
4. [Redactar respuesta de venta (Sesión 01)](#4-redactar-respuesta-de-venta-sesión-01)
5. [Extraer un dato de un documento (Sesión 03)](#5-extraer-un-dato-de-un-documento-sesión-03)
6. [Extracción estructurada en JSON (Sesión 04)](#6-extracción-estructurada-en-json-sesión-04)
7. [Generar el reporte / insights (Sesión 05-06)](#7-generar-el-reporte--insights-sesión-05-06)

Ver también: [curriculum/class-07/lab/scenarios.md](../../curriculum/class-07/lab/scenarios.md) con plantillas completas por industria.

---

## 1. Anatomía del prompt profesional (Sesión 01)

Estructura Rol + Tarea + Contexto + Formato:

```
Actúa como [<!-- rol profesional -->].
Tu tarea es [<!-- qué quieres que haga -->].
Contexto: [<!-- datos relevantes: cliente, situación, etc. -->].
Formato: [<!-- lista, párrafo, JSON, máximo N palabras, idioma, tono -->].
```

---

## 2. Clasificar un correo (Sesión 01)

```
Actúa como [<!-- asesor comercial, soporte, etc. -->].
Clasifica el siguiente correo en una de estas categorías:
[<!-- Venta nueva / Queja / Consulta / Spam -->].
Contexto: [<!-- dato relevante: cliente VIP, factura impaga, etc. -->].
Devuelve la categoría en 1 palabra y una explicación de máximo 2 líneas.

Correo:
[<!-- pega el correo -->]
```

---

## 3. Resumir una reunión (Sesión 01)

```
Actúa como [<!-- tu rol -->].
Resume la siguiente reunión en un resumen ejecutivo.
Formato: 4-5 bullets + una lista de "Acciones siguientes" con responsable.

Notas:
[<!-- pega las notas o la transcripción -->]
```

---

## 4. Redactar respuesta de venta (Sesión 01)

```
Actúa como [<!-- tu rol comercial -->].
Redacta una respuesta para este cliente.
Contexto: [<!-- cotización pendiente, seguimiento, objeción de precio -->].
Formato: tono profesional y cercano. Dame 2 opciones de respuesta.

Mensaje del cliente:
[<!-- pega el mensaje -->]
```

---

## 5. Extraer un dato de un documento (Sesión 03)

Para el módulo de Gemini en el flujo (un solo dato, en texto):

```
Lee esta factura y devuelve SOLO el nombre del proveedor
(la empresa que emite la factura), sin texto adicional.
```

---

## 6. Extracción estructurada en JSON (Sesión 04)

Para el system prompt cuando necesitas varios datos a la vez:

```
Eres un asistente que extrae datos estructurados de [<!-- correos / documentos -->].
Responde SOLO JSON válido, sin markdown ni texto adicional.
Si un campo no está en el texto, usa null (no inventes).

Schema:
{ "fecha": "YYYY-MM-DD" | null,
  "entidad": "nombre",
  "monto_o_metrica": number,
  "tipo": "Nuevo" | "Recurrente" | null,
  "descripcion": "1 línea de contexto" }

TEXTO:
{{1.text}}
```

---

## 7. Generar el reporte / insights (Sesión 05-06)

Para que la IA produzca el contenido del reporte a partir de los datos del Sheet:

```
Eres un analista de [<!-- tu industria -->]. Analiza los datos del período
y devuelve SOLO JSON válido, sin markdown.
Cada hallazgo debe incluir un número específico y, si aplica, una comparación.

CONTEXTO:
- Meta del período: [<!-- meta -->]
- Período anterior: [<!-- valor anterior -->]

DATOS:
{{datos_del_sheet}}

Responde:
{ "resumen": "2-3 oraciones",
  "hallazgo_1": "...",
  "hallazgo_2": "...",
  "riesgo_1": "...",
  "accion_1": "..." }
```
