<p align="right">Idioma:&emsp;<a href="hig.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../../README.es.md) / [Definir la apariencia](../../SKILL.es.md) / [Presets](../presets.es.md)

# Preset hig

Apple Human Interface Guidelines, apariencia light, para iOS, iPadOS y macOS.

Fuente: Human Interface Guidelines, color, tipografía y layout, https://developer.apple.com/design/human-interface-guidelines/color, https://developer.apple.com/design/human-interface-guidelines/typography y https://developer.apple.com/design/human-interface-guidelines/layout. Los estilos de tipo en el tamaño Large Dynamic Type son Large Title 34 pt regular, Title 1 28 pt regular, Headline 17 pt semibold, Body 17 pt regular. SF Pro es la familia del sistema.

El HIG no publica hex para los colores del sistema. El hex del archivo de tokens es la apariencia light en sRGB de los colores nombrados: systemBlue `#007AFF`, systemRed `#FF3B30`, label `#000000`, secondaryLabel `rgb(60, 60, 67)` al 60 % de opacidad, systemBackground `#FFFFFF`, secondarySystemBackground `#F2F2F7`, separator `rgb(60, 60, 67)` al 29 % de opacidad. No los sustituyas por otro azul.

El HIG no publica un token de esquina, un token de sombra ni un token de interlineado junto a los estilos de texto. `radius.grouped` (10 px) es una esquina continua de trabajo para un grupo inset, y `elevation.card` es un sustituto para que el kit tenga un token de elevación (0 1 px 3 px al 12 % de negro). La profundidad en el HIG es un material, no esta sombra. `space.unit` (8 px) es un paso de trabajo. `space.margin` (16 px) es el margen de layout habitual del iPhone. El interlineado del cuerpo en el archivo es 22 pt (multiplicador 1.29). No presentes los valores de trabajo como tokens de Apple, y no los cambies al entregar.

- Plataforma: iOS, iPadOS o macOS
- Temas: light. Los colores nombrados también se adaptan a dark. Dark no está en este preset.
- Guía nativa: Apple Human Interface Guidelines
- Agrupación: la del preset. Botón, campo de texto y texto. Los demás componentes se añaden cuando una pantalla los necesita.

## Cuándo recomendarlo

El producto es iOS, iPadOS o macOS. Nombrar la plataforma no es nombrar este preset.

## Componentes

### Botón

- Para qué se usa: la acción destacada.
- Estados: default, hover, focus, pressed, disabled. No aplican: selected, error, loading.
- Tokens: relleno `theme.light.color.systemBlue`, etiqueta `theme.light.color.systemBackground`. Pressed y hover conservan ese tinte; la plataforma dibuja la apariencia pressed. Hover aplica con un puntero. Focus sigue el anillo de foco de la plataforma. Disabled conserva los mismos colores con menos énfasis; este subconjunto no tiene un segundo hex para él. El tamaño mínimo del control es 44 px. Radio `radius.grouped`. Estilo de la etiqueta `type.headline`.

### Campo de texto

- Para qué se usa: un valor que la persona escribe.
- Estados: default, focus, disabled, error. No aplican: hover, pressed, selected, loading. Hover no aplica al campo en una pantalla táctil.
- Tokens: relleno `theme.light.color.secondarySystemBackground`, texto `theme.light.color.label`, placeholder `theme.light.color.secondaryLabel`. Focus conserva el relleno y usa `theme.light.color.systemBlue` para el cursor. Error usa `theme.light.color.systemRed`; el valor escrito se conserva. Radio `radius.grouped`. Estilo de texto `type.body`.

### Texto

- Para qué se usa: el cuerpo, un título y un título grande.
- Estados: default. No aplican: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: cuerpo `type.body` en `theme.light.color.label`. Título `type.title`. Título grande `type.largeTitle`. Texto secundario en `theme.light.color.secondaryLabel`.

## Tokens

`hig.tokens.json`.
