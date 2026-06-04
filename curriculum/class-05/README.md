> **Sesión 5 de 8** · Plantillas con placeholders

# Sesión 05: Plantillas con placeholders

## Resumen

Ya tienes datos limpios y estructurados en tu Sheet. Hoy los conviertes en **documentos con formato profesional** de forma automática. Aprenderás qué es una **plantilla** (un esqueleto con formato fijo y datos que cambian) y cómo los **placeholders** `{{variable}}` marcan los huecos que Make rellena con datos reales.

Verás cómo **mapear** cada dato a su placeholder, qué módulos usar para generar documentos desde plantillas en **Slides y Docs** (Create from Template), y cómo dar **formato** a fechas, números y monedas antes de inyectarlos. Al terminar, tu escenario consultará el Sheet de facturas y generará un reporte mensual con plantilla, listo para guardarse en Drive o enviarse por correo.

---

## ¿Por qué te sirve?

- **Los reportes repetitivos tienen 80% de formato fijo y 20% de datos que cambian.** Diseñar la plantilla una vez elimina horas de copiar-pegar cada período.
- **Un placeholder bien mapeado convierte una fila del Sheet en un documento presentable** sin que toques el diseño nunca más.
- **Generar Docs y Slides automáticos sirve para mucho más que facturas:** fichas de cliente, cartas, dashboards, presentaciones — el mismo patrón.

---

## 🎯 ¿Qué haremos en clase?

1. **Entenderás qué es una plantilla** y cómo los placeholders `{{variable}}` marcan lo que cambia.
2. **Mapearás datos a placeholders** — el paso clave para que el documento se llene bien.
3. **Usarás Create from Template** en Slides/Docs desde Make.
4. **Generarás un reporte mensual de facturas** con formato de fechas, números y monedas.

---

## Objetivos de Aprendizaje

Al finalizar esta sesión, podrás:

1. **Explicar** qué es una plantilla y cómo funcionan los placeholders `{{variable}}`.
2. **Mapear** cada dato del Sheet a su placeholder en la plantilla.
3. **Generar** un documento o presentación desde una plantilla usando Make (Create from Template).
4. **Aplicar** formato a fechas, números y monedas antes de inyectarlos al documento.

---

## ✅ Preparación para la Clase

### De sesiones anteriores

- Tu Sheet con datos estructurados (Sesión 4): facturas y/o ventas registradas.
- Conexión Google activa en Make (Drive, Sheets, Slides).

### Reflexión previa

Antes de llegar a clase, piensa en:

- ¿Qué reporte o documento armas repetidamente con el mismo formato?
- ¿Qué partes son siempre iguales y cuáles cambian cada vez?

### Herramientas

- [ ] **Google Slides / Docs** — Para diseñar la plantilla.
- [ ] **Tu Sheet con datos** — De la Sesión 4 (facturas / ventas).
- [ ] **Tu escenario de Make** — Donde agregarás el módulo de plantilla.

### Lectura sugerida

- [Crear presentación desde plantilla en Make](https://www.make.com/en/integrations/google-slides){:target="_blank"} — Módulo Create a Presentation from a Template.
- [Funciones de formato en Make](https://www.make.com/en/help/functions){:target="_blank"} — formatDate, formatNumber y más.

---

## Glosario

| Término | Definición |
|---------|------------|
| **Plantilla** | Esqueleto reutilizable: formato fijo, datos variables. |
| **Placeholder** | Marcador `{{variable}}` en la plantilla que Make reemplaza por un dato. |
| **Mapeo** | Asignar qué variable del flujo va en cada placeholder. |
| **Create from Template** | Módulo de Make que genera un Doc/Slide a partir de una plantilla. |
| **formatDate / formatNumber** | Funciones de Make para dar formato a fechas y números antes de inyectarlos. |

---

## Recursos Adicionales

- [Reemplazar texto/imagen en Google Slides](https://support.google.com/docs/answer/6317504){:target="_blank"} — Cómo funciona el reemplazo de marcadores.
- [Plantillas de Google Slides](https://docs.google.com/presentation/u/0/?ftv=1){:target="_blank"} — Galería para inspirarte en el diseño.
