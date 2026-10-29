<p align="right">Idioma:&emsp;<a href="ui-kit.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Definir la apariencia](../SKILL.es.md)

# Kit de interfaz

Fuente de los tokens: Design Tokens Format Module 2025.10 (https://www.w3.org/community/reports/design-tokens/CG-FINAL-format-20251028/) y Design Tokens Color Module 2025.10 (https://www.designtokens.org/TR/2025.10/color/). No son un estándar del W3C. El archivo termina en `.tokens.json`.

## Qué fija

Componentes, tokens y reglas para repetir el diseño. Tokens de color, tipografía, espacio, radio y elevación, por tema.

## Qué deja abierto

La pantalla concreta. El mock y el handoff consumen este kit.

## Tokens

Cada token tiene `$value` y, salvo que lo herede del grupo, `$type`. Un token sin tipo no es válido: no infieras el tipo a partir del valor.

| Uso | `$type` | `$value` |
| --- | --- | --- |
| Color | `color` | Objeto con `colorSpace`, `components` (0–1 en `srgb`), `hex` opcional de 6 dígitos y `alpha` opcional entre 0 y 1 (si falta, es 1) |
| Espacio y radio | `dimension` | `{ "value": <number>, "unit": "px" }` o `"rem"` |
| Familia | `fontFamily` | Un nombre o una lista de nombres |
| Peso | `fontWeight` | Un número 1–1000, o un alias del módulo (`regular`, `bold`, …) |
| Interlineado | `number` | Un multiplicador del tamaño |
| Estilo de texto | `typography` | `fontFamily`, `fontSize`, `fontWeight`, `letterSpacing`, `lineHeight` |
| Elevación | `shadow` | `color`, `offsetX`, `offsetY`, `blur`, `spread`; `inset` cuando aplica |

Un alias es `"{group.token}"`. Los temas del producto son grupos (`theme.light`, `theme.dark`), solo los que existen. `$description` dice para qué sirve el token, en el idioma del artefacto.

Si el producto ya tiene un kit, copia sus valores. No los «mejores». Un cambio de valor es otra entrega o una enmienda, como pida la persona.

Si no lo tiene, lee [presets.es.md](presets.es.md). Copia el preset seleccionado. Si no se selecciona ninguno, copia `plain`. No inventes una sexta paleta. No cambies los valores de un preset.

## Componentes

Agrupa como lo hace el kit del producto. Un preset usa la agrupación de su propio archivo. Si no hay kit ni preset, puedes agruparlos al modo de Atomic Design (Brad Frost) y decirlo en el Markdown. Cada componente lista los estados que le aplican, de esta lista: default, hover, focus, pressed, disabled, selected, error y loading. El que no aplica se dice en una línea.

Las reglas del Markdown dicen cuándo se usa el componente y qué token usa. No escribas el componente en HTML.

## Plantilla Markdown

```markdown
# UI kit — <product>

- Platform:
- Themes:
- Native guide: <none | HIG | Material Design 3 | Fluent 2>. If it contradicts the kit: the kit wins.
- Grouping: the product's | Atomic Design, because there is no kit yet
- Tokens: `<NNN>-ui-kit-<topic>.tokens.json`
- Source: Design Tokens Format Module 2025.10

## Components

### <component>
- Used for:
- States: default, hover, focus, pressed, disabled. Do not apply: selected, error, loading.
- Tokens:
```

## Ejemplo de token

```json
{
  "color": {
    "action": {
      "$type": "color",
      "$description": "Primary action on a light background",
      "$value": { "colorSpace": "srgb", "components": [0, 0.4, 0.8], "hex": "#0066cc" }
    }
  },
  "space": {
    "stack": {
      "$type": "dimension",
      "$value": { "value": 16, "unit": "px" }
    }
  },
  "radius": {
    "control": {
      "$type": "dimension",
      "$value": { "value": 4, "unit": "px" }
    }
  },
  "font": {
    "family": {
      "$type": "fontFamily",
      "$value": "Source Sans 3"
    },
    "weight": {
      "$type": "fontWeight",
      "$value": "regular"
    }
  },
  "type": {
    "body": {
      "$type": "typography",
      "$value": {
        "fontFamily": "{font.family}",
        "fontSize": { "value": 16, "unit": "px" },
        "fontWeight": "{font.weight}",
        "letterSpacing": { "value": 0, "unit": "px" },
        "lineHeight": 1.5
      }
    }
  },
  "elevation": {
    "panel": {
      "$type": "shadow",
      "$value": {
        "color": { "colorSpace": "srgb", "components": [0, 0, 0], "alpha": 0.12, "hex": "#000000" },
        "offsetX": { "value": 0, "unit": "px" },
        "offsetY": { "value": 2, "unit": "px" },
        "blur": { "value": 8, "unit": "px" },
        "spread": { "value": 0, "unit": "px" }
      }
    }
  }
}
```

El color de la sombra sigue Color Module 2025.10: `alpha` entre 0 y 1, y un `hex` de 6 dígitos sin el canal alfa. No uses un borrador posterior del formato.

## Prerrequisitos

- **Valores.** Un kit `accepted`, el color, el tipo, el espacio, el radio y la elevación en este turno, o un preset de [presets.es.md](presets.es.md). Si no llega ninguno, usa el preset `plain` y registra la plantilla `plain` bajo Assumed, nombrando `dense`, `material-3`, `hig` y `fluent-2`. Estado: `accepted`. Cámbialo con `/uiux-ui-kit`. Regenera con `/uiux-ui-kit`.

## Indicaciones

La pieza se escribe sin este prompt. `plain` ya es el kit. Para elegir otro, o para pasar valores:

```text
/uiux-ui-kit for the shop. Preset plain.
Other presets: dense, material-3, hig, fluent-2.
Or the values: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

No hay un comando anterior.

## Terminado

- El archivo de tokens es `.tokens.json`. Cada token tiene `$value` y `$type` (el suyo o heredado del grupo). Los valores de color, dimension, font, number, typography y shadow coinciden con el módulo. No se infirió un tipo a partir del valor.
- Los temas son solo los que el producto tiene. Un kit `accepted` se copió, no se mejoró. Si no, el archivo es el preset nombrado, los valores de este turno, o el preset `plain` cuando no se seleccionó ninguno. Los valores del preset no se cambiaron. No se inventó una sexta paleta.
- `notas` nombra el id del preset cuando se usó un preset. Cuando `plain` fue el de partida, la respuesta nombra `dense`, `material-3`, `hig` y `fluent-2`.
- Cada componente lista los estados que aplican y dice cuáles no. Las reglas nombran el token. Sin HTML. La pantalla concreta no se dibuja.
