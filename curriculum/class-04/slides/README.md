<!-- .slide: data-background="#0A192F" -->

# SESIÓN 4
## JSON + PARSE JSON

Que la IA devuelva datos estructurados, no charla

*Sesión 4 de 8 · 60 minutos · Online en vivo*

---

## TRANSICIÓN · DE UN DATO A VARIOS

### La sesión pasada:

- Gemini extrajo UN dato (el proveedor)
- En texto libre

### Hoy:

- La IA devuelve **varios datos juntos**, ordenados
- Cada campo cae en su columna automáticamente

> "Hoy domesticamos lo que la IA devuelve."

---

## QUÉ VAMOS A LOGRAR HOY

### OBJETIVO DE LA SESIÓN

Procesar la respuesta estructurada de la IA con Parse JSON y un Data Structure para convertir texto en variables.

### FUNDAMENTOS

1. ¿Qué es JSON?
2. Por qué pedirle a la IA que responda en JSON
3. Data Structure en Make (el "molde")
4. Parse JSON + variables resultantes

### MINI-PROYECTO

Extracción de ventas desde Gmail

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿La IA te devolvió una respuesta tan larga que no sabías qué hacer con ella?

**02** ¿Cómo extraes datos de un texto largo hoy (a mano, copy/paste)?

**03** ¿Te tocó parsear un Excel a mano para subirlo a otro sistema?

> 💡 JSON es el formato que hace que la IA hable un idioma que tu flujo entiende.

---

## FUNDAMENTO 1 · ¿QUÉ ES JSON?

*Formato estándar de datos*

Objetos `{}`, arrays `[]`, pares clave-valor:

```json
{
  "vendedor": "Ana",
  "cliente": "Acme S.A.",
  "monto": 1500,
  "fecha": "2026-06-01"
}
```

---

## FUNDAMENTO 2 · POR QUÉ PEDIR JSON A LA IA

*Texto libre = imposible de procesar*

| SIN JSON (texto libre) | CON JSON (estructurado) |
|------------------------|-------------------------|
| "Ana vendió a Acme..." | `{ "vendedor": "Ana", ... }` |
| Hay que adivinar el dato | Cada dato en su clave |
| Frágil | Robusto |

> Lo pides en el **system prompt**: "responde SOLO en JSON".

---

## FUNDAMENTO 3 · DATA STRUCTURE EN MAKE

*El "molde" que le dices a Make*

- Defines el **nombre** de cada campo (vendedor, monto...)
- Defines el **tipo** (texto, número, fecha)
- Make genera **variables** para los módulos siguientes
- Si la IA devuelve algo distinto al molde → error claro

---

## EJEMPLO REAL · DATA STRUCTURE "VENTA"

*El molde del JSON que llega desde Gemini*

```
MAKE · Data Structures · Venta
──────────────────────────────────
vendedor   Text          ✓ requerido
cliente    Text          ✓ requerido
producto   Text          ✓ requerido
monto      Number        ✓ requerido
fecha      Date (ISO)    ✓ requerido
tipo       Text          ✗ opcional
```

---

## FUNDAMENTO 4 · PARSE JSON + VARIABLES

*Convierte el texto en objeto*

- **TEXTO JSON** — lo que devolvió la IA
- **PARSE JSON** — lo convierte usando el molde
- **VARIABLES** — vendedor, monto, fecha... listas para usar

> Cada campo queda como una variable que arrastras al Sheet.

---

## MINI-PROYECTO · VENTAS DESDE GMAIL

*Correo informal → JSON → columnas del Sheet*

**Individual**

### QUÉ HACER

1. Configurar **Gmail Watch** en Make (correos de vendedores)
2. Diseñar el **system prompt**: JSON con vendedor, cliente, producto, monto, fecha
3. Crear el **Data Structure** (el molde del JSON)
4. Agregar el módulo **Parse JSON**
5. Mapear cada variable a su columna del Sheet **"Ventas"**
6. Probar enviando un correo de venta

✓ **Verificación:** El Sheet "Ventas" se llena solo al llegar un correo

---

## LO QUE TE LLEVAS HOY

**01** Saber pedirle a la IA que responda en JSON

**02** Data Structure + Parse JSON funcionando

**03** Sheet de ventas alimentado desde Gmail

### PRÓXIMA SESIÓN

Sesión 5: Plantillas con placeholders. Convertimos estos datos en documentos automáticos.
