> **Sesión 6 de 8** · Flujo end-to-end robusto

# Sesión 06: Flujo end-to-end robusto

## Resumen

Ya construiste cada pieza por separado: prompts, Make, Gemini, JSON y plantillas. Hoy las unes en **un solo flujo completo** que va de Drive → IA → Sheets/Docs → Gmail, y lo haces **robusto** para que aguante el mundo real. Aprenderás cuándo conviene un trigger por evento (**Watch**) o programado (**Schedule**), y cómo usar **filtros y routers** para que el flujo decida solo qué procesar y por qué ruta.

Sobre todo, aprenderás a que el flujo **no falle en silencio**: manejo de errores con reintentos, notificaciones cuando algo se cae, y **logs** para depurar. Al terminar, tendrás el flujo completo de facturas funcionando de punta a punta, con filtros, un router y alertas — un sistema de producción, no una demo.

---

## ¿Por qué te sirve?

- **Un flujo de juguete falla en silencio; uno robusto te avisa antes que el cliente.** La diferencia entre los dos son los filtros, el error handler y los logs.
- **Los filtros evitan procesar basura** (archivos que no son facturas, datos vacíos) y ahorran operaciones.
- **Saber depurar con el History de Make te vuelve autónomo** — puedes arreglar tu propio flujo sin depender de nadie.

---

## 🎯 ¿Qué haremos en clase?

1. **Distinguirás Watch vs Schedule** y cuándo usar cada trigger.
2. **Agregarás filtros y routers** para que el flujo decida qué procesar y por qué ruta.
3. **Configurarás manejo de errores y notificaciones** para que el flujo avise si algo falla.
4. **Unirás todo en el flujo completo de facturas** y lo probarás con casos límite.

---

## Objetivos de Aprendizaje

Al finalizar esta sesión, podrás:

1. **Decidir** entre un trigger Watch (por evento) y Schedule (programado) según el caso.
2. **Configurar** filtros y routers para añadir lógica condicional al flujo.
3. **Implementar** manejo de errores con notificaciones y revisar logs para depurar.
4. **Integrar** las piezas de las sesiones anteriores en un flujo end-to-end robusto.

---

## ✅ Preparación para la Clase

### De sesiones anteriores

- Tus escenarios de Make con Gemini, Parse JSON y plantilla (Sesiones 2-5).
- El Sheet de facturas y la plantilla de reporte funcionando.

### Reflexión previa

Antes de llegar a clase, piensa en:

- ¿Qué pasaría si llega un archivo que NO es una factura a tu carpeta?
- Si tu flujo se cayera un viernes, ¿cómo te enterarías?

### Herramientas

- [ ] **Tus escenarios de Make** de las sesiones anteriores.
- [ ] **Un par de archivos "difíciles"** (un no-PDF, una factura sin total) para probar casos límite.

### Lectura sugerida

- [Filtros y routers en Make](https://www.make.com/en/help/tools/flow-control){:target="_blank"} — Control de flujo.
- [Manejo de errores en Make](https://www.make.com/en/help/errors/error-handling){:target="_blank"} — Error handlers y reintentos.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Watch** | Trigger por evento: dispara cuando algo cambia (ej: archivo nuevo). |
| **Schedule** | Trigger programado: dispara a una hora/intervalo fijo. |
| **Filtro** | Condición que deja pasar solo lo que cumple un criterio. |
| **Router** | Bifurcación que envía cada caso por una ruta distinta. |
| **Error handler** | Módulo que se activa si un paso falla (reintento, notificación). |
| **Log** | Registro de cada ejecución para depurar (History de Make). |

---

## Recursos Adicionales

- [History y depuración en Make](https://www.make.com/en/help/scenarios/scenario-history){:target="_blank"} — Ver qué pasó en cada corrida.
- [Reintentos y break en Make](https://www.make.com/en/help/errors/error-handlers){:target="_blank"} — Tipos de manejo de error.
