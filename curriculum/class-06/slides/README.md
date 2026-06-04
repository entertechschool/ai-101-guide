<!-- .slide: data-background="#0A192F" -->

# SESIÓN 6
## FLUJO END-TO-END ROBUSTO

Un proceso completo que aguanta el mundo real

*Sesión 6 de 8 · 60 minutos · Online en vivo*

---

## TRANSICIÓN · DE PIEZAS A SISTEMA

### Las sesiones pasadas:

- Prompts, Make, Gemini, JSON, plantillas
- Cada pieza por separado

### Hoy:

- Unimos todo en **un flujo completo**
- Que aguanta errores, datos raros y feriados

> "Hoy pasas de un escenario simple a un sistema en producción."

---

## QUÉ VAMOS A LOGRAR HOY

### OBJETIVO DE LA SESIÓN

Diseñar un flujo completo Drive → IA → Sheets/Docs/Gmail que automatiza un proceso real de principio a fin.

### FUNDAMENTOS

1. Trigger por evento (Watch) vs programado (Schedule)
2. Filtros y routers — lógica condicional
3. Manejo de errores y notificaciones
4. Logs y depuración

### MINI-PROYECTO

Flujo completo de facturas: Drive → IA → Sheets → Docs → Email

---

## APERTURA · 10 min

*Responde por chat — 1 línea por pregunta*

**01** ¿Alguna vez se cayó un proceso tuyo y nadie se enteró hasta tarde?

**02** ¿Tu flujo actual aguanta feriados, datos raros o formatos distintos?

**03** Si tu flujo se rompe mañana, ¿cómo te enteras?

> 💡 Un flujo de juguete falla en silencio. Uno robusto te avisa antes que el cliente.

---

## FUNDAMENTO 1 · WATCH VS SCHEDULE

*Cuándo usar cada trigger*

| WATCH (por evento) | SCHEDULE (programado) |
|--------------------|-----------------------|
| Dispara cuando algo cambia | Dispara a una hora fija |
| Tiempo real | Por lotes |
| Ej: archivo nuevo en Drive | Ej: reporte cada lunes 8am |

---

## FUNDAMENTO 2 · FILTROS Y ROUTERS

*Que el flujo decida por sí solo*

- **FILTRO:** "solo seguir si el archivo es PDF"
- **ROUTER:** "si es factura → ruta A, si es boleta → ruta B"
- Evita procesar lo que no debe procesarse
- Permite manejar varios casos en un solo escenario

---

## EJEMPLO REAL · UN FILTRO EN MAKE

*Solo procesa facturas PDF con monto > 0*

```
MAKE · Filter Configuration
──────────────────────────────────
Label: Solo PDF con monto > 0

 File extension  equals  "pdf"
        AND
 Monto detected  greater than  0

✓ Match:    continúa al siguiente módulo
✗ No match: salta este registro
```

---

## FUNDAMENTO 3 · MANEJO DE ERRORES

*Que el flujo no muera en silencio*

- Error handler en cada módulo crítico
- Reintentos automáticos (3 intentos con espera)
- Notificación por email/Slack si se cae
- Que el flujo siga con el próximo item, no se detenga

---

## FUNDAMENTO 4 · LOGS Y DEPURACIÓN

*Saber qué pasó en cada corrida*

- El **History** de Make muestra cada ejecución
- Verde = éxito, rojo = error
- Clic en cada módulo para ver entrada/salida
- **Run once** con datos de prueba sin gastar operaciones

---

## MINI-PROYECTO · FLUJO COMPLETO DE FACTURAS

*Drive → IA → Sheets → Docs → Email*

**Individual**

### QUÉ HACER

1. Integrar S2-S5 en un solo escenario
2. Agregar **filtros** (solo PDF, monto > 0)
3. Agregar **router** (facturas grandes → alerta; normales → registro)
4. Agregar **error handler** + notificación al jefe si algo falla
5. Probar con casos límite (factura sin total, archivo corrupto)

✓ **Verificación:** Flujo completo que aguanta el mundo real y avisa si se rompe

---

## LO QUE TE LLEVAS HOY

**01** Flujo end-to-end corriendo de inicio a fin

**02** Filtros, routers y manejo de errores configurados

**03** Confianza en que el flujo no muere en silencio

### PRÓXIMA SESIÓN

Sesión 7: Aplicas todo a TU caso real. Construyes tu proyecto integrador propio.
