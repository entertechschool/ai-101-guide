> **Sesión 3 de 8** · API key de Gemini

# Sesión 03: API key de Gemini

## Resumen

Hasta ahora tu flujo solo copiaba el nombre del archivo. Hoy metes **inteligencia** dentro del escenario: conectas **Gemini** a Make para que lea cada factura y extraiga datos automáticamente. Para eso vas a entender qué es una **API** (el puente entre tu flujo y la IA) y una **API key** (tu llave personal y secreta), que generarás gratis en **Google AI Studio**.

Aprenderás también la diferencia entre guardar la credencial como una **Connection** reutilizable en Make versus pegar la key a mano, y cuándo conviene el modelo **Gemini Flash** (rápido y económico) frente a **Pro**. Al terminar, tu escenario subirá una factura, Gemini leerá el documento y el nombre del proveedor caerá solo en una columna del Sheet.

---

## ¿Por qué te sirve?

- **Una API key es lo que conecta cualquier IA con tus herramientas.** Es la misma llave que abre la puerta a automatizar casi cualquier tarea con IA, no solo facturas.
- **Dejar que la IA lea documentos elimina la transcripción manual.** Lo que hoy lees y copias a mano, Gemini lo extrae en segundos dentro del flujo.
- **Entender Connection vs key directa te ahorra problemas de seguridad.** Aprendes a manejar credenciales sin exponerlas — clave para cualquier sistema serio.

---

## 🎯 ¿Qué haremos en clase?

1. **Entenderás qué es una API y una API key** — el puente y la llave entre tu flujo y la IA.
2. **Generarás tu API key** gratis en Google AI Studio y la guardarás de forma segura.
3. **Distinguirás Connection vs key directa** y los modelos Gemini Flash vs Pro.
4. **Sumarás Gemini al escenario de la Sesión 2** para que lea la factura y extraiga el proveedor.

---

## Objetivos de Aprendizaje

Al finalizar esta sesión, podrás:

1. **Explicar** qué es una API y qué es una API key, y por qué la key es secreta.
2. **Generar** una API key de Gemini en Google AI Studio.
3. **Distinguir** entre una Connection de Make y una API key directa, y entre los modelos Flash y Pro.
4. **Integrar** un módulo de Gemini en un escenario de Make para extraer un dato de un documento.

---

## ✅ Preparación para la Clase

### De sesiones anteriores

- Tu escenario de Make **Drive → Sheet** funcionando (Sesión 2).
- Conexión Google activa en Make (Cloud Project con Client ID/Secret).

### Reflexión previa

Antes de llegar a clase, piensa en:

- ¿Qué documentos recibes (facturas, comprobantes, formularios) de los que extraes datos a mano?
- ¿Qué dato concreto te gustaría que la IA leyera y registrara por ti?

### Herramientas

- [ ] **Google AI Studio** — Accederás a [aistudio.google.com](https://aistudio.google.com/){:target="_blank"} para crear tu API key (gratis).
- [ ] **Tu escenario de Make** — El de la Sesión 2 (Drive → Sheet).

### Lectura sugerida

- [Obtener una API key de Gemini](https://ai.google.dev/gemini-api/docs/api-key){:target="_blank"} — Guía oficial de Google AI Studio.
- [Modelos de Gemini](https://ai.google.dev/gemini-api/docs/models){:target="_blank"} — Diferencias entre Flash y Pro.

---

## Glosario

| Término | Definición |
|---------|------------|
| **API** | Puente que permite a una app pedirle algo a otra de forma estructurada. |
| **API key** | Llave personal y secreta para usar una API; se asocia a tu cuenta. |
| **Google AI Studio** | Plataforma de Google donde generas tu API key de Gemini y pruebas prompts. |
| **Connection (Make)** | Credencial guardada en Make que se reutiliza en cualquier escenario. |
| **Gemini Flash** | Modelo rápido y económico, ideal para tareas simples de alto volumen. |
| **Gemini Pro** | Modelo más capaz y costoso, para análisis complejo. |

---

## Recursos Adicionales

- [Gemini en Make](https://www.make.com/en/integrations/google-ai){:target="_blank"} — Módulos de Google AI / Gemini disponibles.
- [Buenas prácticas con API keys](https://ai.google.dev/gemini-api/docs/api-key#keep-safe){:target="_blank"} — Cómo no exponer tu credencial.
