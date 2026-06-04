> **Sesión 2 de 8** · Make 101 + Google Cloud

# Sesión 02: Make 101 + Google Cloud

## Resumen

Hoy construyes tu primer flujo automatizado **real** — sin escribir código. Vas a conocer Make, la plataforma donde conectas apps como bloques en un tablero, y entenderás cómo viajan los datos de una app a otra mediante **OAuth** (el permiso que le das a Make para usar tu Google sin compartir tu contraseña).

Para que esa conexión funcione, crearás un **Google Cloud Project** que genera las credenciales (Client ID + Secret) que Make necesita. Al terminar tendrás un escenario corriendo solo: cada vez que subes una factura a una carpeta de Drive, aparece automáticamente una fila en tu Google Sheet. Todavía sin IA — eso llega en la Sesión 3.

---

## ¿Por qué te sirve?

- **Conectar dos apps sin programar es la base de toda automatización.** Una vez que entiendes el patrón trigger → módulos → acción, puedes automatizar casi cualquier proceso repetitivo.
- **OAuth es lo que hace seguro todo esto.** Aprendes a autorizar apps sin entregar tu contraseña — una habilidad que aplica a cualquier herramienta no-code.
- **El registro automático de facturas elimina la transcripción manual.** Lo que hoy haces copiando y pegando, el flujo lo hará solo en segundos.

---

## 🎯 ¿Qué haremos en clase?

1. **Entenderás qué es Make** y cómo funciona un escenario (trigger → módulos → acción).
2. **Aprenderás OAuth** — cómo una app autoriza a otra sin compartir contraseñas.
3. **Crearás un Google Cloud Project** con Client ID y Secret para conectar tu cuenta Google.
4. **Armarás tu primer escenario:** subir una factura a Drive registra una fila en un Sheet, automáticamente.

---

## Objetivos de Aprendizaje

Al finalizar esta sesión, podrás:

1. **Explicar** qué es Make y describir la anatomía de un escenario.
2. **Explicar** cómo funciona OAuth y por qué evita compartir tu contraseña.
3. **Crear** un Google Cloud Project y generar las credenciales (Client ID + Secret).
4. **Construir** un escenario Drive → Sheets que registra archivos nuevos automáticamente.

---

## ✅ Preparación para la Clase

### De sesiones anteriores

- Tus 3 prompts profesionales de la Sesión 1 (los reusaremos cuando entre la IA).

### Reflexión previa

Antes de llegar a clase, piensa en:

- ¿Qué proceso de tu trabajo implica recibir un archivo o correo y copiar datos a otro lado?
- ¿Cuántas facturas, documentos o registros manejas al mes?

### Herramientas

- [ ] **Cuenta de Google** — La misma que usas para Drive y Sheets.
- [ ] **Cuenta de Make** — Regístrate gratis en [make.com](https://make.com/){:target="_blank"} (sin tarjeta).
- [ ] **Google Cloud** — Accederás a [console.cloud.google.com](https://console.cloud.google.com/){:target="_blank"} en clase para crear el proyecto.

### Lectura sugerida

- [¿Qué es Make?](https://www.make.com/en/how-it-works){:target="_blank"} — Introducción visual a la plataforma.
- [Cómo funciona OAuth (explicado simple)](https://support.google.com/cloud/answer/6158849){:target="_blank"} — Documentación de Google sobre credenciales OAuth.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Make** | Plataforma no-code para conectar apps y automatizar flujos visualmente. |
| **Escenario** | Un flujo automático en Make: trigger → módulos → acción. |
| **Trigger** | El evento que dispara el escenario (ej: un archivo nuevo en Drive). |
| **Módulo** | Cada bloque del escenario que representa una acción de una app. |
| **OAuth** | Permiso que le das a una app para usar tu cuenta sin compartir tu contraseña. |
| **Google Cloud Project** | Contenedor donde Google guarda la config de tu app y genera credenciales. |
| **Client ID / Secret** | Las credenciales que Make necesita para conectarse a tu Google vía OAuth. |

---

## Recursos Adicionales

- [Documentación de Google Drive en Make](https://www.make.com/en/integrations/google-drive){:target="_blank"} — Módulos disponibles (Watch Files, etc.).
- [Crear credenciales OAuth en Google Cloud](https://developers.google.com/workspace/guides/create-credentials){:target="_blank"} — Guía paso a paso oficial.
