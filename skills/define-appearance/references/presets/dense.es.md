<p align="right">Idioma:&emsp;<a href="dense.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../../README.es.md) / [Definir la apariencia](../../SKILL.es.md) / [Presets](../presets.es.md)

# Preset dense

El mismo color que `plain`, con tipo, espacio y radio más apretados. Para una herramienta web, una tabla o un backoffice. No hay estándar externo: el color es `plain`, y las medidas más apretadas pertenecen a este plugin.

- Plataforma: web
- Temas: light
- Guía nativa: ninguna
- Agrupación: la del preset. Botón, campo de texto y texto. Los demás componentes se añaden cuando una pantalla los necesita.

## Cuándo recomendarlo

El producto es una herramienta web con tablas o un backoffice, y `plain` a 16 px quedaría demasiado holgado. No es el de partida.

## Componentes

### Botón

- Para qué se usa: la acción primaria de una pantalla densa.
- Estados: default, hover, focus, pressed, disabled. No aplican: selected, error, loading.
- Tokens: los mismos roles de color que `plain`. Radio `radius.control` (2 px). Separación interior horizontal `space.controlX`, separación interior vertical `space.controlY`. Estilo de la etiqueta `type.label`.

### Campo de texto

- Para qué se usa: un valor que la persona escribe, incluido un filtro.
- Estados: default, hover, focus, disabled, error. No aplican: pressed, selected, loading.
- Tokens: los mismos roles de color que `plain`. Radio `radius.control`. Separación interior `space.controlX` y `space.controlY`. Estilo de texto `type.body`. El error conserva lo que se escribió.

### Texto

- Para qué se usa: texto de lectura, un título de pantalla y una celda de tabla.
- Estados: default. No aplican: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: cuerpo y celda de tabla `type.body` en `theme.light.color.text`. Título `type.title`. Texto secundario en `theme.light.color.textMuted`.

## Tokens

`dense.tokens.json`. El color coincide con `plain`. El cuerpo es 14 px. La pila es 8 px. El radio del control es 2 px. La sombra del panel es 0 1 px 4 px al 12 % de negro.
