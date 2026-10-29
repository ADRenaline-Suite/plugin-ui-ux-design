<p align="right">Idioma:&emsp;<a href="plain.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../../README.es.md) / [Definir la apariencia](../../SKILL.es.md) / [Presets](../presets.es.md)

# Preset plain

Punto de partida por defecto para un producto web sin marca. Lectura cómoda. No hay estándar externo: estos valores pertenecen a este plugin.

- Plataforma: web
- Temas: light
- Guía nativa: ninguna
- Agrupación: la del preset. Botón, campo de texto y texto. Los demás componentes se añaden cuando una pantalla los necesita.

## Cuándo recomendarlo

Web, sin marca, y nadie ha elegido un preset. Si no se selecciona ninguno, este es el que se escribe.

## Componentes

### Botón

- Para qué se usa: la acción primaria de la pantalla.
- Estados: default, hover, focus, pressed, disabled. No aplican: selected, error, loading.
- Tokens: relleno default `theme.light.color.action`, etiqueta `theme.light.color.onAction`. Relleno hover `theme.light.color.actionHover`. Relleno pressed `theme.light.color.actionPressed`. Focus usa el mismo relleno que default y un contorno de 2 px en `theme.light.color.action`. Relleno disabled `theme.light.color.disabled`, etiqueta `theme.light.color.onDisabled`. Radio `radius.control`. Separación interior horizontal `space.controlX`, separación interior vertical `space.controlY`. Estilo de la etiqueta `type.label`.

### Campo de texto

- Para qué se usa: un valor que la persona escribe.
- Estados: default, hover, focus, disabled, error. No aplican: pressed, selected, loading.
- Tokens: relleno `theme.light.color.background`, texto `theme.light.color.text`, borde `theme.light.color.border`. Hover y focus usan un borde de 2 px en `theme.light.color.action`. El borde de error y el aviso de error usan `theme.light.color.error`; el valor escrito se conserva. Relleno disabled `theme.light.color.disabled`, texto `theme.light.color.onDisabled`. Radio `radius.control`. Separación interior `space.controlX` y `space.controlY`. Estilo de texto `type.body`.

### Texto

- Para qué se usa: el texto de lectura y el título de la pantalla.
- Estados: default. No aplican: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: cuerpo `type.body` en `theme.light.color.text`. Título `type.title` en `theme.light.color.text`. Texto secundario `type.body` en `theme.light.color.textMuted`.

## Tokens

`plain.tokens.json`. Color, tipo, espacio, radio y elevación. Los pasos de espacio son 8, 16 y 32. El radio de un control es 4 px. La sombra del panel es 0 2 px 8 px al 12 % de negro.
