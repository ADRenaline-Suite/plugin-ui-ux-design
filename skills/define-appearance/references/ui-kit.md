# UI kit

Source of the tokens: Design Tokens Format Module 2025.10 (https://www.w3.org/community/reports/design-tokens/CG-FINAL-format-20251028/) and Design Tokens Color Module 2025.10 (https://www.designtokens.org/TR/2025.10/color/). They are not a W3C standard. The file ends in `.tokens.json`.

## What it fixes

Components, tokens, and rules for repeating the design. Tokens for color, typography, space, radius, and elevation, per theme.

## What it leaves open

The concrete screen. The mock and the handoff consume this kit.

## Tokens

Each token has `$value` and, unless it inherits it from the group, `$type`. A token without a type is invalid: do not infer the type from the value.

| Use | `$type` | `$value` |
| --- | --- | --- |
| Color | `color` | Object with `colorSpace`, `components` (0–1 in `srgb`), optional 6-digit `hex`, and optional `alpha` between 0 and 1 (if missing, it is 1) |
| Space and radius | `dimension` | `{ "value": <number>, "unit": "px" }` or `"rem"` |
| Family | `fontFamily` | A name or a list of names |
| Weight | `fontWeight` | A number 1–1000, or an alias from the module (`regular`, `bold`, …) |
| Line height | `number` | A multiplier of the size |
| Text style | `typography` | `fontFamily`, `fontSize`, `fontWeight`, `letterSpacing`, `lineHeight` |
| Elevation | `shadow` | `color`, `offsetX`, `offsetY`, `blur`, `spread`; `inset` when it applies |

An alias is `"{group.token}"`. The product's themes are groups (`theme.light`, `theme.dark`), only the ones that exist. `$description` says what the token is for, in the language of the artifact.

If the product already has a kit, copy its values. Do not "improve" them. A change of value is another delivery or an amendment, as the user asks.

## Components

Group them as the product's kit does. If there is no kit, you may group them in the manner of Atomic Design (Brad Frost) and say so in the Markdown. Each component lists the states that apply to it, from this list: default, hover, focus, pressed, disabled, selected, error, and loading. The one that does not apply is said in one line.

The Markdown rules say when the component is used and which token it uses. Do not write the component in HTML.

## Markdown template

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

## Token example

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

The shadow color follows Color Module 2025.10: `alpha` between 0 and 1, and a 6-digit `hex` without the alpha channel. Do not use a later draft of the format.

## Prerequisites

- **Values.** Color, type, space, radius, and elevation, in this turn. If the product already has a kit, start from that one. Stops the delivery. No earlier command.

## Prompts

In one message:

```text
/uiux-ui-kit for the shop. Web platform, light theme.
Action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

There is no earlier command. The single prompt is the way.
