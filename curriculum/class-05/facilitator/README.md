# Guía del Facilitador - Clase 05: Tu Primer Agente IA

> Tiempo de lectura: 10 minutos | Prepárate antes de clase

---

## Conceptos Clave

- **Agente IA**: Automatización que usa IA para DECIDIR, no solo ejecutar reglas fijas.
- **Form → Webhook → OpenRouter → Gmail**: La arquitectura completa del agente.
- **SystemPrompt**: Define el ROL y REGLAS del agente (lo que "es"). Permanente.
- **UserPrompt**: Mapea los datos de cada mensaje (lo que "recibe"). Cambia por mensaje.
- **v0**: Genera formularios con IA — refuerzo de Few-shot (C02) y Socio pensante (C03).
- **Supervisión**: Un agente no reemplaza al humano — prioriza su trabajo.

---

## Analogías Útiles

**Agente como recepcionista inteligente:**
Un recepcionista no reenvía todos los mensajes al mismo lugar. Lee, decide quién debe atenderlo, y lo direcciona. Tu agente hace exactamente eso — y te manda un email con la decisión.

**Automatización vs agente:**
Automatización = contestador automático ("Presione 1 para soporte, 2 para ventas"). Agente = recepcionista que LEE tu mensaje y decide a quién derivarte.

**SystemPrompt como manual del empleado:**
Si contratas a alguien y no le das instrucciones claras, tomará malas decisiones. El SystemPrompt ES el manual de tu agente.

**UserPrompt como la bandeja de entrada:**
El SystemPrompt dice "eres un agente de triage con estas reglas". El UserPrompt dice "acaba de llegar este mensaje de María López". Uno es permanente, el otro cambia con cada caso.

**Errores del agente como errores de un junior:**
Un empleado nuevo se equivoca. No lo despides — le das mejor contexto. Con el agente igual: errores = oportunidad de mejorar el SystemPrompt.

---

## Contexto Actual

### Por qué triage como caso base

La conexión C02 → C05 es intencional y potente:
- En C02, los estudiantes ya clasificaron estos mismos mensajes manualmente
- Entienden los criterios, los errores esperados y las limitaciones
- Ver su trabajo manual convertido en agente automático es un "momento wow" genuino
- Pueden comparar resultados: manual vs automático con los mismos datos

### Por qué esta arquitectura

| Decisión | Razón |
|----------|-------|
| Form en v0 (no curl/JSON manual) | Origen de datos tangible, refuerza M1, menos intimidante |
| Make (no Zapier) | Más visual, plan free generoso, módulo OpenRouter nativo |
| OpenRouter nativo (no HTTP genérico) | SystemPrompt + UserPrompt separados, sin JSON manual |
| Gmail (no Router + 3 rutas) | Una sola acción de salida, menos complejidad |
| Gemini como clarificador | Ya la conocen de C04, refuerza socio pensante de C03 |
| Template pre-armado (3 módulos) | Reduce fricción técnica, foco en personalización |

### Nota sobre MAX_TWO_NEW_TOOLS

Esta clase introduce 3 herramientas nuevas: Make, v0 y OpenRouter/Grok. La regla se flexibiliza porque v0 es un vehículo pedagógico que refuerza M1 (Few-shot, Socio pensante), no una herramienta central del curso. Gemini ya es conocida de C04.

### El riesgo técnico

Esta es la clase más técnica del curso. Los estudiantes son profesionales no-técnicos. Riesgos:
- **API keys**: Concepto nuevo, puede generar confusión
- **Webhooks**: Concepto abstracto hasta que lo ven funcionar
- **v0 deploy**: Puede fallar o tardar
- **Permisos Gmail**: Make necesita autorización de Gmail
- **Make UI**: Puede sentirse abrumador al inicio

**Mitigación:** Template de 3 módulos (no 4+) + formulario de backup + facilitador con demo lista + enfoque en personalización, no construcción desde cero.

---

## Preparación ANTES de Clase (Crítico)

### Lo que DEBES tener listo:

1. **Formulario de backup en v0**
   - Crea y despliega un formulario de PetShop Express funcional
   - Tenlo listo como plan B si algún estudiante no puede crear el suyo
   - Comparte la URL como fallback

2. **Template de Make funcionando**
   - Crea el escenario con 3 módulos: Webhook → OpenRouter → Gmail
   - Configura OpenRouter con SystemPrompt + UserPrompt separados
   - Pruébalo con los 5 mensajes de PetShop Express
   - Verifica que los emails llegan correctamente
   - Genera el link de clonación para estudiantes

3. **Wireframe base**
   - Prepara un wireframe simple de formulario de contacto
   - Los estudiantes lo usarán como ejemplo para v0 (Few-shot)
   - Puede ser un screenshot de un form existente

4. **API Key de OpenRouter de respaldo**
   - Ten una key propia como backup
   - Grok Free tiene límites — verifica que funcione antes de clase

5. **Demo ejecutada y verificada**
   - Corre la demo completa: enviar desde form → ver email con clasificación
   - Guarda screenshots de backup de cada paso
   - Verifica que Gmail autoriza el envío desde Make

---

## Los 5 Mensajes (Mismos de C02)

El mismo set de PetShop Express. Los estudiantes ya los conocen:

| # | Mensaje | En C02 (manual) | Esperado en C05 (agente) |
|---|---------|-----------------|--------------------------|
| 1 | Perro dieta especial, pedido retrasado | La mayoría lo clasificó urgente | URGENTE (salud animal) |
| 2 | Rascador para gatos consulta | Baja/Venta | VENTA o CONSULTA (ambiguo, aceptable ambos) |
| 3 | Cliente enojado, quiere reembolso | Muchos lo pusieron urgente por tono | Puede priorizar tono sobre realidad (error esperado) |
| 4 | Factura "no urgente" pero deadline viernes | Error más común de C02 | Si el SystemPrompt no tiene regla de deadlines, falla igual |
| 5 | Vitaminas que no funcionaron | Categoría ambigua | Depende del SystemPrompt: ¿Queja? ¿Consulta? |

### El momento pedagógico clave

Cuando el agente comete los MISMOS errores que en C02:
- "¿Recuerdan que en C02 la IA confundía tono con urgencia? Miren — el agente hace lo mismo"
- "El agente es tan bueno como el SystemPrompt. Si no agregaron la regla de deadlines, falla igual"

---

## Momentos Clave de la Clase

### Pregunta Detonadora (~5 min)

**Respuesta correcta:** B — Un agente usa IA para tomar decisiones

**Script post-votación:**
```
Facilitador: "¿Quién votó D, que no hay diferencia? Buen debate.
La diferencia es esta: si tu regla de email dice 'todo a soporte',
eso es automatización. Si una IA LEE el email y DECIDE si va a
soporte, ventas o se responde con FAQ, eso es un agente.
La IA introduce DECISIÓN en el flujo."
```

---

### Demo Principal: Agente en Vivo (~10 min)

**Preparación:** Ten tu formulario v0 abierto y el escenario de Make activo. Usa 3 mensajes para la demo.

**Script sugerido:**
```
Facilitador: "Voy a enviar 3 mensajes desde este formulario. Observen."
[Abre el formulario v0 en pantalla, llena y envía mensaje 1]
Facilitador: "El mensaje viajó del formulario al webhook de Make.
Veamos qué hizo la IA..."
[Muestra Make History — clasificación como URGENTE]
Facilitador: "Correcto. Y miren mi email — llegó con la categoría y acción."
[Muestra Gmail con el email recibido]
[Envía mensaje 2 desde el formulario]
Facilitador: "Este lo clasificó como VENTA. Mismo flujo, decisión diferente."
[Envía mensaje 3]
Facilitador: "¿Qué creen que hizo con este? ¿URGENTE por el tono?"
[Muestra resultado]
Facilitador: "¿Recuerdan C02? El tono agresivo no siempre es urgencia real."
```

**Si algo sale mal:**
- Si Grok tarda: "Modelos gratuitos a veces son lentos. En producción pagas por velocidad"
- Si clasifica mal: "Perfecto — miren el error. ¿Qué cambiarían en el SystemPrompt?"
- Si Make falla: Usa screenshots de backup
- Si v0 no carga: Usa el formulario de backup que pre-armaste

---

### Transición a Parte 2: Crear Form con v0 (~2 min)

**Script sugerido:**
```
Facilitador: "Antes de armar el agente, necesitan de DÓNDE vienen los datos.
Van a crear su propio formulario con v0 — una IA que genera interfaces.
¿Recuerdan Few-shot de C02? Van a usar el mismo principio:
adjunten un ejemplo visual y v0 genera algo similar.
Y si no saben qué estilo elegir, usen Gemini como en C03 —
pídanle 3 opciones y elijan."
```

---

### Transición a Parte 3: Construir Agente en Make (~2 min)

**Script sugerido:**
```
Facilitador: "Ahora que tienen su formulario, vamos al agente.
Les doy un template con 3 módulos. Su trabajo es personalizar:
1. El SystemPrompt — las categorías y reglas (lo que el agente ES)
2. El UserPrompt — cómo mapean los datos del form (lo que el agente RECIBE)
3. Gmail — a dónde llega el email con la clasificación"
```

---

### Transición a Parte 4: Probar (~1 min)

**Script sugerido:**
```
Facilitador: "Activen su escenario y envíen los 5 mensajes de PetShop Express
desde SU formulario. Revisen su Gmail — deberían tener 5 emails
con la clasificación de cada mensaje."
```

---

## Errores Esperados de Estudiantes

| Señal | Qué está pasando | Qué hacer |
|-------|------------------|-----------|
| "No puedo crear la API key" | Confusión con OpenRouter | Guiar paso a paso o prestar key de backup |
| "v0 no genera lo que quiero" | Prompt poco específico o sin wireframe | "Adjunta tu wireframe como ejemplo — Few-shot visual" |
| "v0 no me deja hacer deploy" | Cuenta limitada o error temporal | Compartir formulario de backup pre-armado |
| "No sé qué estilo usar para el form" | Parálisis de decisión | "Abre Gemini y pídele 3 opciones — elige una y sigue" |
| "Make no me deja clonar" | Problema de cuenta o permisos | Verificar cuenta free activa |
| "Gmail no se conecta en Make" | Permisos de Google no autorizados | Guiar autorización de Gmail en Make paso a paso |
| "El agente no responde" | Webhook no activo o form no conectado | Verificar escenario ON + URL del webhook correcta en el form |
| "Siempre clasifica todo igual" | SystemPrompt genérico o sin categorías claras | "Revisa tu SystemPrompt — ¿tiene categorías específicas?" |
| "Esto es muy técnico para mí" | Intimidación ante APIs y webhooks | "Lo técnico ya está en el template. Tu trabajo es el PROMPT — eso ya sabes desde C02" |

---

## Preguntas Frecuentes

### "¿Esto funciona con ChatGPT o Claude?"
Sí. El patrón form → webhook → IA → acción es universal. Hoy usamos Grok por ser gratuito, pero el SystemPrompt funciona con cualquier modelo.

### "¿Cuánto cuesta mantener un agente?"
Make free = 1,000 operaciones/mes. Grok free = sin costo. Para uso personal es suficiente.

### "¿Puede el agente responder directamente al cliente?"
Puede, pero NO debería sin supervisión humana. La configuración segura: el agente CLASIFICA y te envía la decisión. Tú decides la acción final.

### "¿Qué pasa si el agente se equivoca?"
Lo mismo que cuando un empleado nuevo se equivoca: le das mejor contexto (mejor SystemPrompt), más reglas, y supervisas hasta que sea confiable.

### "¿Por qué no usamos un módulo HTTP genérico?"
Porque el módulo nativo de OpenRouter en Make separa SystemPrompt y UserPrompt visualmente. Es más intuitivo y no requiere escribir JSON manual.

### "¿Qué pasa si Gemini no está disponible para un estudiante?"
Gemini es opcional — es el clarificador de estilo para v0. Si no funciona, el estudiante puede elegir estilo por cuenta propia o usar el wireframe base.

---

## Checkpoints de Validación

| Minuto | Checkpoint | Cómo validar |
|--------|------------|--------------|
| ~5 | Pregunta detonadora | Manos levantadas, participación |
| ~15 | Demo completa | "¿Vieron cómo cada email fue diferente?" |
| ~45 | Formulario v0 deployado | "¿Quién tiene su form funcionando?" |
| ~55 | Template clonado | "¿Quién tiene los 3 módulos en Make?" |
| ~80 | SystemPrompt + UserPrompt | "¿Quién ya personalizó ambos prompts?" |
| ~90 | Gmail configurado + form conectado | "¿Quién tiene todo conectado?" |
| ~105 | 5 mensajes enviados | "¿Quién recibió los 5 emails?" |
| ~115 | Análisis crítico | "¿Qué errores encontraron?" |

---

## Sección Anti-Hype: Cómo Manejarla

**Script para introducir limitaciones:**
```
Facilitador: "Antes de probar, una advertencia:
Su agente se va a equivocar. Garantizado.
Si recuerdan C02, la IA confundía tono agresivo con urgencia real.
Su agente va a hacer lo mismo — a menos que su SystemPrompt lo corrija.
La diferencia: en C02 el error era uno. Con un agente,
el error se repite automáticamente en cada mensaje.
Por eso el SystemPrompt importa MÁS en un agente que en uso manual."
```

**Los 4 puntos a enfatizar:**
1. Basura entra, basura sale — ahora a escala
2. La IA no tiene sentido común — deadlines ocultos
3. Supervisión no es opcional — el agente prioriza, no reemplaza
4. Automatizar un mal proceso = errores más rápidos

---

## Tips de Facilitación

### Si el grupo tiene mucha fricción técnica:
- Prioriza que TODOS tengan el formulario de backup y el template clonado
- Si alguien no puede crear API key, presta la de backup
- Si v0 falla, comparte tu formulario pre-armado inmediatamente
- Es mejor un agente con SystemPrompt default funcionando que uno personalizado que no corre

### Si el grupo avanza rápido:
- Que personalicen categorías de su trabajo real (no PetShop)
- Que envíen mensajes reales (anonimizados)
- Que experimenten cambiando reglas del SystemPrompt y viendo cómo cambia la clasificación

### Si alguien está intimidado:
- "Lo más técnico ya está hecho. El template es como un carro armado — tú decides el destino (SystemPrompt) y qué llevas (UserPrompt)"
- Emparejar con alguien que va bien

### Si alguien quiere ir más allá de Make:
- "Make es para aprender el patrón. El principio form → IA → acción funciona en n8n, Zapier, o código. Domina el patrón aquí."

---

## Conexión con la Próxima Clase

Al cerrar, planta la semilla:

> "Hoy crearon un agente que DECIDE por ustedes basándose en un SystemPrompt.
> Pero el agente no los CONOCE — no sabe quién son, qué hacen, ni qué prefieren.
> La próxima clase: una IA que trabaja con SUS documentos,
> conoce SU contexto y responde desde SU conocimiento.
> Segundo cerebro con NotebookLM + Claude personalizado."

**Tarea para mencionar:**
Google Doc con: URL del form v0, screenshot del flujo en Make, SystemPrompt + UserPrompt, tabla de resultados con 5 mensajes, 1 falla documentada.
