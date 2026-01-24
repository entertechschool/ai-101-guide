---
name: lint-markdown
description: Valida Markdown para GitHub Pages: enlaces externos, escape de Liquid en código. Usar para revisar links, validar markdown, o antes de push.
allowed-tools: Read, Glob, Grep, Edit, WebFetch
---

# Lint Markdown - Validador para GitHub Pages

## Validaciones Incluidas

1. **Enlaces externos sin `{:target="_blank"}`** - Kramdown/Jekyll
2. **Código con `{{` sin escape Liquid** - Evita errores de build
3. **Enlaces rotos (HTTP 404)** - Verificación de URLs externas

---

## Proceso General

### Paso 1: Determinar alcance

Por defecto escanear `curriculum/` recursivamente. Si el usuario especifica un archivo o carpeta, usar ese alcance.

### Paso 2: Ejecutar validaciones

Ejecutar las tres validaciones y reportar resultados combinados.

---

## Validación 1: Enlaces Externos

### Definiciones

**Enlace externo:** URL que comienza con `http://` o `https://`

**Enlace interno:**
- Anclas: `#seccion`
- Rutas relativas: `./archivo.md`, `../carpeta/`
- Sin protocolo

### Formato Correcto (Kramdown)

```markdown
[texto](https://url-externa.com){:target="_blank"}
```

### Detección

Usar Grep para encontrar enlaces externos sin target:
```regex
\[([^\]]+)\]\((https?://[^)]+)\)(?!\{:target)
```

Explicación:
- `\[([^\]]+)\]` - Captura el texto del enlace
- `\((https?://[^)]+)\)` - Captura URL que empieza con http(s)://
- `(?!\{:target)` - Negative lookahead: NO seguido de `{:target`

### Corrección

Agregar `{:target="_blank"}` después del enlace:
```markdown
[Google](https://google.com){:target="_blank"}
```

---

## Validación 2: Escape Liquid para Jekyll

### Problema

GitHub Pages usa Jekyll, que interpreta `{{` como sintaxis de Liquid. Esto causa errores de build cuando hay código con dobles llaves.

### Error típico
```
Liquid syntax error: Variable '{{ width: `${...}' was not properly terminated
```

### Detección

Buscar bloques de código con `{{`:
```regex
```(jsx|javascript|js|tsx|ts|json)[\s\S]*?\{\{
```

### Solución

Envolver bloques de código que contienen `{{` con tags raw/endraw de Jekyll:

````markdown
{% raw %}
```json
{
  "config": {{ "value" }}
}
```
{% endraw %}
````

### Proceso

1. Buscar bloques de código con `{{`
2. Verificar si ya tienen `{% raw %}` antes
3. Si no lo tienen, agregar `{% raw %}` antes del bloque y `{% endraw %}` después

---

## Validación 3: Enlaces Rotos (HTTP 404)

### Objetivo

Verificar que los enlaces externos devuelven HTTP 200 (o redirección válida).

### Proceso

1. Extraer todos los enlaces externos únicos (`https?://`) del alcance
2. Para cada enlace único, usar WebFetch para verificar accesibilidad
3. Reportar enlaces que devuelven 404 o error de conexión

### Consideraciones

- **Límite por ejecución:** Máximo 10 enlaces únicos por ejecución para evitar rate limiting
- **Caché de sesión:** Si un enlace ya fue verificado en la sesión actual, no repetir
- **Timeout/Error:** Si WebFetch falla con error de conexión, reportar como "No verificable"
- **Redirecciones:** Son válidas si el destino final existe (301/302 → 200 = OK)
- **Prioridad:** Verificar primero enlaces en archivos modificados recientemente

### Detección

Usar Grep para extraer URLs únicas:
```regex
https?://[^\s\)\]"']+
```

### Reporte de Estado

| Estado | Significado |
|--------|-------------|
| ✅ 200 | Enlace válido |
| ↪️ 301/302 | Redirección válida |
| ❌ 404 | Enlace roto - requiere corrección |
| ⚠️ Error | No verificable (timeout, conexión) |

---

## Reporte de Resultados

**Modo reporte (default):**

```markdown
## Reporte de Validación Markdown

### Enlaces sin target="_blank"

| Archivo | Línea | Enlace |
|---------|-------|--------|
| class-01/lab/README.md | 23 | [Claude](https://claude.ai/) |

**Total:** X enlaces a corregir

### Bloques de código sin escape Liquid

| Archivo | Línea | Lenguaje |
|---------|-------|----------|
| class-02/slides/README.md | 45 | json |

**Total:** Y bloques a corregir

### Enlaces rotos (HTTP 404)

| Archivo | Línea | URL | Estado |
|---------|-------|-----|--------|
| class-01/README.md | 73 | https://anthropic.com/... | ❌ 404 |

**Total:** W enlaces rotos
**Verificados:** N de M enlaces únicos

### Sin problemas: Z archivos
```

---

## Ejemplos de Uso

**Escanear todo:**
```
/lint-markdown
```

**Escanear archivo específico:**
```
/lint-markdown curriculum/class-01/lab/README.md
```

**Corregir automáticamente:**
```
/lint-markdown --fix
```

---

## Enlaces Comunes en AI 101

### Herramientas (verificar periódicamente)
- https://claude.ai
- https://chat.openai.com
- https://gemini.google.com
- https://perplexity.ai
- https://make.com
- https://zapier.com
- https://notion.so

### Documentación
- https://docs.anthropic.com
- https://platform.openai.com/docs
- https://ai.google.dev

---

## Notas

- NO modificar enlaces internos (anclas, rutas relativas)
- NO modificar enlaces en bloques de código (``` o `)
- Preservar cualquier otro atributo Kramdown existente
- Siempre verificar build de GitHub Pages después de cambios
- Los enlaces a herramientas de IA cambian frecuentemente - revisar cada módulo
