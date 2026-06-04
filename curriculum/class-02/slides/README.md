<!-- .slide: data-background="#0A192F" -->

# SESIÓN 2
## MAKE 101 + GOOGLE CLOUD

Tu primer flujo automatizado real

*Sesión 2 de 8 · 60 minutos · Online en vivo*

---

## TRANSICIÓN · DE PROMPTS A FLUJOS

### La sesión pasada:

- Escribiste 3 prompts profesionales
- Aprendiste a pedir output libre vs estructurado

### Hoy:

- Conectas dos apps **sin programar**
- Tu primer escenario corriendo solo en Make

> "Hoy dejamos de pedirle cosas a la IA a mano y empezamos a automatizar."

---

## QUÉ VAMOS A LOGRAR HOY

### OBJETIVO DE LA SESIÓN

Construir un primer escenario en Make conectando una cuenta Google vía OAuth.

### FUNDAMENTOS

1. ¿Qué es Make?
2. Anatomía de un escenario
3. OAuth — cómo una app autoriza a otra
4. Google Cloud Project — para qué se necesita

### MINI-PROYECTO

Registro automático de facturas: Drive → Sheet (sin IA aún)

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿Conectaste alguna vez dos apps sin programar?

**02** ¿Cuántas facturas o documentos manejas al mes?

**03** Si pudieras automatizar UN proceso de tu trabajo, ¿cuál sería?

> 💡 Make + Google es el primer paso para que esos procesos se hagan solos.

---

## FUNDAMENTO 1 · ¿QUÉ ES MAKE?

*Plataforma no-code para conectar apps*

- Un "tablero" donde conectas bloques que representan apps
- Drive, Sheets, Gmail, Gemini... todos se enlazan
- **Sin escribir una línea de código**

> Cada bloque hace una cosa; tú decides el orden.

---

## FUNDAMENTO 2 · ANATOMÍA DE UN ESCENARIO

*Trigger → módulos → acción*

- **TRIGGER** — lo que dispara el flujo (ej: archivo nuevo en Drive)
- **MÓDULOS** — procesan los datos en el medio
- **ACCIÓN** — el resultado final (ej: fila en un Sheet)

> Un escenario = una receta automática.

---

## FUNDAMENTO 3 · OAUTH

*El permiso que le das a Make sin compartir tu contraseña*

1. Make pide acceso a tu Google
2. Te redirige al login de Google
3. Apruebas los permisos específicos
4. Google le da un "token" a Make
5. Make usa el token — tu contraseña nunca se comparte

---

## FUNDAMENTO 4 · GOOGLE CLOUD PROJECT

*Para qué se necesita*

- Un "contenedor" donde Google guarda la config de tu app
- Genera **Client ID + Client Secret** (las credenciales que Make pide)
- Habilitas las APIs que vas a usar (Drive, Sheets...)

> Sin esto, ciertos conectores no autentican.

---

## EJEMPLO REAL · CLIENTE OAUTH EN CLOUD CONSOLE

*Lo que copias en Make para conectar tu cuenta*

```
GOOGLE CLOUD CONSOLE · Credentials
──────────────────────────────────
Nombre:        Make Google Drive
Tipo:          Aplicación web
Client ID:     8214...apps.googleusercontent.com
Client Secret: ****qGV3   [👁 Ver]
Estado:        ✓ Habilitada
```

---

## MINI-PROYECTO · REGISTRO DE FACTURAS

*Drive → Sheet, sin IA aún*

**Individual**

### QUÉ HACER

1. Crear cuenta Make + Google Cloud Project (Client ID + Secret)
2. Crear carpeta Drive **"Facturas-Entrada"**
3. Crear Sheet **"Facturas-Registro"** (archivo, fecha, link)
4. Armar escenario: **Drive Watch Files → Sheets Add a Row**
5. Probar con **Run once**: subir una factura, ver la fila

✓ **Verificación:** Cada factura nueva en Drive aparece sola en el Sheet

---

## LO QUE TE LLEVAS HOY

**01** Cuenta Make + Google Cloud Project configurados

**02** Entiendes OAuth y por qué necesita Client ID/Secret

**03** Tu primer escenario corriendo: Drive → Sheets

### PRÓXIMA SESIÓN

Sesión 3: API key de Gemini. Metemos IA dentro de este flujo para que lea las facturas.
