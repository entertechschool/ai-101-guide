# Guía del Facilitador - Clase 06: Tu Agente Inteligente

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Branching/Routing**: Un flujo que se divide en múltiples caminos según condiciones.
- **Router**: Módulo de Make que crea las rutas. Cada ruta tiene un Filter.
- **Filter**: Condición que activa una ruta (ej: "output contains URGENTE").
- **Logging**: Registrar cada decisión del agente en Google Sheets (timestamp + datos + categoría).
- **Agente multi-acción**: Un agente que no solo decide — actúa diferente según la decisión.

---

## Analogías Útiles

**Router como recepcionista con 3 puertas:**
El Router es una recepcionista que lee la clasificación y abre una puerta diferente: puerta roja para urgentes, puerta azul para consultas, puerta verde para ventas. Cada puerta lleva a una acción diferente.

**Google Sheets como bitácora del agente:**
Un agente sin registro es como un empleado que trabaja pero no anota nada. ¿Cómo sabes si está haciendo bien su trabajo? La bitácora (Sheets) te permite auditar, mejorar y demostrar resultados.

**Flujo lineal vs branching:**
Flujo lineal = autopista de un solo carril — todos van al mismo destino. Branching = carretera con desvíos — cada carro toma la salida según su destino.

---

## Preparación ANTES de Clase (Crítico)

### Lo que DEBES tener listo:

1. **Tu escenario de C05 funcionando** (Webhook → OpenRouter)
   - Actualizado con Gmail → probado end-to-end
   - Ten un escenario con Router + 3 rutas + Sheets como backup/demo

2. **Gmail autorizado en Make**
   - Prueba la autorización con tu cuenta
   - Conoce los pasos exactos para guiar a estudiantes
   - Error más común: permisos de Google → "Allow" en cada paso

3. **Google Sheets de backup**
   - Crea una hoja con las 6 columnas: Timestamp | Nombre | Email | Mensaje | Categoría | Acción
   - Compártela como modelo para que los estudiantes repliquen la estructura

4. **5 mensajes de PetShop Express listos**
   - Los mismos de C02 y C05. Tenlos en un documento para compartir durante el battle
   - Define las clasificaciones "correctas" de antemano para la votación

5. **Demo completa ejecutada**
   - Enviar mensaje → ver email con emoji de categoría → ver registro en Sheets
   - Tener screenshots de backup de cada paso

---

## Momentos Clave de la Clase

### Momento WOW: Gmail funciona (~20 min)

Este es el momento más importante de la clase. Cuando el primer email llega con la clasificación:

**Script sugerido:**
```
Facilitador: "Envíen un mensaje desde su formulario..."
[Estudiantes envían]
Facilitador: "Revisen su Gmail... ¿llegó?"
[Espera reacciones]
Facilitador: "Su agente recibió, pensó y les avisó.
Sin que hicieran nada. ESO es un agente."
```

**Si el email no llega:**
- Verificar que el escenario esté ON
- Verificar permisos de Gmail en Make
- Revisar Make History para ver si hubo error
- Revisar carpeta de Spam

---

### Pregunta Detonadora (~5 min)

**Respuesta correcta:** D — Email diferente + registro

**Script post-votación:**
```
Facilitador: "Si tu agente clasifica URGENTE y CONSULTA pero
manda el mismo email para ambos... ¿para qué clasificó?
La clasificación solo tiene valor si produce ACCIÓN diferente.
Y el registro es lo que te permite mejorar el agente con datos."
```

---

### Transición a Router (~2 min)

**Script sugerido:**
```
Facilitador: "Ahora su agente envía email. Pero es el MISMO email
para todo — urgente, consulta, venta. ¿Tiene sentido que un
mensaje urgente reciba la misma respuesta que una consulta?
Vamos a agregar inteligencia: el Router."
```

---

### Momento clave: Router ejecuta rutas diferentes

Cuando los estudiantes ven en Make History que el Router tomó rutas diferentes para mensajes diferentes — ese es el segundo WOW moment.

```
Facilitador: "Miren Make History. ¿Ven cómo el Router tomó
la ruta roja para el mensaje 1 y la ruta azul para el 2?
Mismo agente, decisiones diferentes. ESO es branching."
```

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "Gmail no se conecta" | Permisos de Google no autorizados | Guiar paso a paso: Make → Gmail → Authorize → Allow ALL |
| "El Router solo usa 1 ruta" | Filters mal configurados o SystemPrompt inconsistente | Verificar: ¿el output dice "URGENTE" exacto? ¿El Filter usa "contains"? |
| "Google Sheets no registra" | Mapeo de columnas incorrecto | Verificar que las columnas en Make coincidan con la hoja |
| "Mi Filter no matchea" | Mayúsculas vs minúsculas | "contains" es case-sensitive — verificar que SystemPrompt produce categorías en el formato exacto |
| "Router ejecuta ruta equivocada" | Filter demasiado amplio | Ej: "VENTA" matchea si el texto dice "preventa" — ser más específico |
| "Mi agente solo clasifica todo como CONSULTA" | SystemPrompt sin reglas claras | Revisar reglas de categorización, especialmente para urgencia |
| "No sé qué columnas poner en Sheets" | Confusión con el mapeo | Compartir la hoja de backup como modelo |

---

## Facilitando el Battle

### Preparación:
1. Comparte los 5 mensajes exactos (mismos para todos)
2. Define clasificaciones "correctas" de antemano:
   - Mensaje 1 (perro dieta): URGENTE (salud animal + retraso)
   - Mensaje 2 (rascador gatos): CONSULTA o VENTA (ambiguo, aceptar ambos)
   - Mensaje 3 (reembolso enojado): CONSULTA (tono ≠ urgencia)
   - Mensaje 4 (factura viernes): URGENTE (deadline real oculto)
   - Mensaje 5 (vitaminas): CONSULTA (queja sin urgencia temporal)

### Durante el battle:
```
Facilitador: "Todos enviaron los mismos 5 mensajes.
Revisen su Google Sheets — ¿cuántos clasificó correctamente?
¿Quién tiene más aciertos?"
[Dar 5 min para comparar]
Facilitador: "Ahora lo interesante: ¿por qué los resultados son diferentes
si TODOS usan el mismo modelo? La respuesta está en el SystemPrompt."
```

### Votación:
- Pide a 2-3 estudiantes que compartan su SystemPrompt
- El grupo vota cuál es más claro/efectivo
- Discusión: ¿qué regla marcó la diferencia?

---

## Sección Anti-Hype

**Script para Router:**
```
Facilitador: "El Router parece mágico — pero solo hace una cosa:
comparar texto. Si tu SystemPrompt dice 'Urgente' con minúscula
y tu Filter busca 'URGENTE' con mayúscula, falla.
Router no piensa. Solo compara strings."
```

**Script para Sheets:**
```
Facilitador: "Google Sheets registra datos. No los analiza por ti.
Tener 100 filas en Sheets no te dice nada automáticamente.
Tú tienes que mirar los datos y decidir qué mejorar."
```

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~5 | Pregunta detonadora | Discusión sobre acción diferenciada |
| ~15 | Gmail conectado | "¿Quién recibió su primer email?" |
| ~20 | WOW moment | Reacciones al email automático |
| ~35 | Router agregado | "¿Quién tiene 3 rutas en el Router?" |
| ~45 | Filters configurados | "¿Quién ve rutas diferentes en History?" |
| ~55 | Google Sheets registrando | "¿Quién tiene datos en su hoja?" |
| ~60 | Test completo (3 mensajes) | "¿Cada email tiene emoji correcto?" |
| ~85 | Battle completado | "¿Quién acertó más clasificaciones?" |
| ~95 | Entregable documentado | Google Doc actualizado |

> ⚠️ El checkpoint más crítico es Gmail (~min 15). Si alguien no puede conectar Gmail, ayúdalo inmediatamente — sin Gmail no puede continuar.

---

## ✅ Señales de Comprensión

**ENTIENDE cuando:**
- Explica por qué el Router necesita Filters exactos (no "inteligentes")
- Puede diagnosticar un Filter que no matchea (case-sensitivity, formato)
- Entiende que Google Sheets es para auditar, no para que el agente "aprenda"

**NECESITA AYUDA cuando:**
- Espera que el Router "entienda" el mensaje — confunde Router con IA
- No puede conectar por qué el logging importa ("ya sé que clasifica bien")
- Sus Filters son demasiado amplios o demasiado estrictos

---

## 🔀 Diferenciación

**Estudiantes avanzados:** Que agreguen una 4ta ruta al Router, que creen Filters más sofisticados (ej: urgente + deadline), que analicen patrones en su Google Sheets.

**Estudiantes con dificultades:** Empezar con solo 2 rutas (URGENTE vs TODO LO DEMÁS), verificar que Gmail funcione antes de agregar Router.

---

## 🎭 Dinámicas de Clase

### "¿A qué puerta va?"
```
Facilitador: [Lee mensaje] "¿Puerta roja (URGENTE), azul (CONSULTA) o verde (VENTA)?"
[Estudiantes votan con la mano. Luego envían al agente]
"¿El agente coincidió con ustedes? Si no, ¿por qué?"
```

---

## 💡 Ejemplos Listos para Usar

### Filters para el Router:
| Ruta | Filter (en Make) | Emoji sugerido |
|------|-----------------|---------------|
| URGENTE | `output` contains `URGENTE` | 🔴 |
| CONSULTA | `output` contains `CONSULTA` | 🔵 |
| VENTA | `output` contains `VENTA` | 🟢 |

---

## ❓ Preguntas Frecuentes

### "¿Por qué no usar un solo email para todo?"
Porque la acción pierde valor. Si un cliente urgente recibe el mismo email que una consulta, ¿para qué clasificamos?

### "¿Google Sheets puede analizar automáticamente?"
Sheets registra. Analizar es tu trabajo (por ahora). En cursos avanzados se pueden conectar dashboards.

---

## 🪞 Reflexión Post-Clase

1. **¿El WOW moment de Gmail funcionó?** — Es el momento más importante de la clase.
2. **¿El battle generó aprendizaje?** — Si todos tuvieron el mismo resultado, el battle no sirvió.
3. **¿Los Filters causaron frustración?** — Si sí, considerar un paso más guiado en el lab.
4. **¿Quiénes no terminaron?** — Identificar para que lleguen a C07 con el agente completo.

---

## Tips de Facilitación

### Si el grupo tiene fricción con Gmail:
- Guiar autorización paso a paso en pantalla compartida
- Si Google bloquea, intentar con otro navegador
- Último recurso: usar el email del facilitador como destino temporal

### Si el grupo avanza rápido:
- Que personalicen categorías a su trabajo real
- Que agreguen una 4ta ruta (ej: SPAM o FEEDBACK)
- Que creen filtros más sofisticados (ej: urgente + deadline)

### Si alguien está intimidado:
- "El Router es como un IF/ELSE visual. Ya sabes la lógica desde C02"
- Emparejar con alguien que va bien

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "Ahora tienen un agente que decide, actúa diferente y registra todo.
> PetShop fue el entrenamiento. Próxima clase: construyen un agente
> para SU caso real de trabajo. Mismo patrón, su contexto.
> Empiecen a pensar: ¿qué proceso de TU trabajo podría ser un agente?"

**Tarea para mencionar:**
1. Google Doc completo (C05+C06) con: form v0, agente completo (5+ módulos), resultados battle, Google Sheets log, análisis crítico.
2. Identificar 1 proceso manual de su trabajo + 5 mensajes reales de ese proceso.
