<!-- .slide: data-background="#0A192F" -->

# SESIÓN 2
## GOOGLE SHEETS CON IA

Diseña la fuente de datos del proyecto

*2.5 horas · IA estratégica para Profesionales*

---

## QUÉ VAMOS A LOGRAR

*Aprendizaje esperado · Puntos clave · Evaluación*

### APRENDIZAJE ESPERADO

Utiliza Gemini para diseñar la estructura del Sheet del proyecto de instrucción con datos crudos, configuración e histórico, dejándolo listo para automatización.

### PUNTOS CLAVE

1. Diseñar VentasSemanaActual con columna Descripción
2. Construir Config con parámetros del negocio
3. Construir Historico para comparativas
4. Usar Gemini para fórmulas y estructura
5. Definir rangos nombrados

### EVALUACIÓN

- Sheet con 3 pestañas funcionando
- 15 filas de datos ejemplo
- Tabla de parámetros actualizada

---

## Apertura · 10 min

### Tu realidad actual de datos

**01 · QUÉ MANEJAS**
¿Qué datos manejas cada semana?
Escribe 3 tipos en el chat.

**02 · DÓNDE**
¿Cómo los tienes organizados?
Excel, Notion, papel, cabeza.

**03 · QUÉ DUELE**
¿Qué te cuesta más consolidar?
Identifica tu dolor real.

---

## POR QUÉ LA IA NECESITA ESTRUCTURA

*Arquitectura de 3 pestañas + rangos nombrados*

**15 min · Teoría**

- Datos en tabla vs datos en texto libre
- Make necesita columnas consistentes
- Gemini necesita contexto + comparables
- **VentasSemanaActual** = datos crudos diarios
- **Config** = parámetros que no cambian (meta, vendedores)
- **Historico** = memoria que se acumula semana a semana

---

## DISEÑA · PESTAÑA VENTASSEMANAACTUAL

*Gemini te sugiere la estructura y genera datos ejemplo*

**40 min · Individual**

### QUÉ HACER

1. Crea nuevo Google Sheet
2. Pide al Gem columnas para capturar ventas diarias
3. Columnas: Fecha, Vendedor, Cliente, Producto, Monto, Tipo, Descripción
4. Pide 15 filas de datos ejemplo y pégalas
5. Actualiza la tabla de parámetros

✓ **Verificación:** Pestaña con 15 filas ejemplo + tabla actualizada

---

## CONSTRUYE · PESTAÑA CONFIG

*Parámetros del negocio que no cambian semana a semana*

**25 min · Individual**

### QUÉ HACER

1. Crea pestaña 'Config'
2. Pide al Gem qué parámetros necesita un reporte
3. Llena: Meta semanal, Ticket objetivo, Vendedores
4. Usa valores reales de TU negocio
5. Registra cada parámetro en la tabla

✓ **Verificación:** Config con al menos 4 parámetros definidos

---

## CONSTRUYE · PESTAÑA HISTORICO

*La memoria que permite comparar semana a semana*

**35 min · Individual**

### QUÉ HACER

1. Crea pestaña 'Historico'
2. Columnas: Semana, Ventas_Total, Clientes_Nuevos, Ticket, Meta_Cumplida
3. Llena 2-3 filas con datos simulados
4. Define rangos nombrados: RangoVentas, RangoConfig, RangoHistorico
5. Actualiza tabla de parámetros

✓ **Verificación:** 3 pestañas funcionando con rangos nombrados

---

## LO QUE TE LLEVAS HOY

*Los artefactos que construiste hoy*

**01** Google Sheet con 3 pestañas estructuradas

**02** 15 filas de datos ejemplo listos para pruebas

**03** Rangos nombrados configurados para Make

**04** Tabla de parámetros con columnas y valores

### PRÓXIMA SESIÓN

Sesión 3: Diseñaremos la plantilla de Google Slides del reporte. Nombraremos todos los marcadores y los conectaremos a este Sheet.
