<p align="right">Idioma:&emsp;<a href="moodboard.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Definir la apariencia](../SKILL.es.md)

# Moodboard

El moodboard no tiene un estándar único en las fuentes de este plugin. Registra la dirección visual para poder repetirla en el kit de interfaz y en los mocks.

## Qué fija

Referencias (enlaces que dio la persona), color, tipo y tono, aplicados a pantallas de ejemplo.

## Qué deja abierto

Los tokens formales y los estados de cada componente. Eso es el kit de interfaz.

## Cómo hacerlo

1. Las referencias son enlaces o piezas que proporcionó la persona. No busques una galería ni inventes otras marcas como si pertenecieran al producto. Si no se proporciona ninguna, aplica la plantilla `neutral` y deja la entrega `proposed`.
2. Un SVG por pantalla de ejemplo. Muestras de color en rectángulos con su hex, una línea de tipo en la familia que nombró la persona, y un bloque de pantalla en ese tono. `xmlns="http://www.w3.org/2000/svg"` y `viewBox`. Sin `foreignObject`.
3. El tono se dice con ejemplos de sí y de no que dio la persona. Si no dio ninguno, describe el tono en una frase y no escribas el microtexto: eso es `plugin-ux-writing`.
4. Si el producto ya tiene un kit de interfaz, el moodboard no lo sustituye. Muestra cómo se aplica el kit.

## Plantilla

```markdown
# Moodboard — <direction>

- Platform:
- References:
- Color:
- Type:
- Tone:
- SVG: `<NNN>-moodboard-<topic>-<screen>.svg`
- Left open: tokens and component states
```

## Ejemplo

Dirección «tienda clara». Referencia: la guía que pasó la persona. Muestra de color `#0066cc` sobre fondo `#ffffff`, una línea en la familia que nombró, y un bloque de pago con ese acento. El SVG es la muestra, no el handoff.

## Prerrequisitos

- **Referencias visuales.** Enlaces o piezas que proporciona quien pide el moodboard. No se busca una galería. Si no llega ninguna, plantilla `neutral`: escala de grises (`#f4f4f4`, `#ffffff`, stroke `#222`), `font-family="system-ui, Segoe UI, sans-serif"`, tono «claro y directo», y la línea de referencias dice que no se proporcionó ninguna. Estado: `proposed`. Cámbialo con `/uiux-moodboard`. Regenera con `/uiux-moodboard`.

## Indicaciones

En un mensaje:

```text
/uiux-moodboard of the shop.
Reference: <url or piece you paste>.
Light theme, accent #0066cc, background #ffffff, type Source Sans 3.
```

No hay un comando anterior. El único prompt es el camino.

## Terminado

- Las referencias son enlaces o piezas que proporcionó la persona, o la plantilla `neutral` cuando no se proporcionó ninguna. No se buscó una galería y no se añadió otra marca como si fuera la del producto. Cuando se usó `neutral`, la entrega es `proposed` y Assumed lo dice.
- Cada pantalla de ejemplo tiene un SVG con `xmlns` y un `viewBox`, una muestra de color con su hex, y el tipo que nombró la persona. Sin `foreignObject`.
- El tono usa los ejemplos de sí y de no de la persona, o una frase si no dio ninguno. No se escribió microtexto. Los tokens y los estados de los componentes quedan abiertos. Un kit existente no se sustituyó.
