<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="dense.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../../README.md) / [Define the appearance](../../SKILL.md) / [Presets](../presets.md)

# Preset dense

The same color as `plain`, with tighter type, space, and radius. For a web tool, a table, or a backoffice. No external standard: the color is `plain`, and the tighter measures belong to this plugin.

- Platform: web
- Themes: light
- Native guide: none
- Grouping: the preset's. Button, text field, and text. Other components are added when a screen needs them.

## Recommend when

The product is a web tool with tables or a backoffice, and `plain` at 16 px would be too loose. It is not the default.

## Components

### Button

- Used for: the primary action of a dense screen.
- States: default, hover, focus, pressed, disabled. Do not apply: selected, error, loading.
- Tokens: the same color roles as `plain`. Radius `radius.control` (2 px). Horizontal padding `space.controlX`, vertical padding `space.controlY`. Label style `type.label`.

### Text field

- Used for: one value the person types, including a filter.
- States: default, hover, focus, disabled, error. Do not apply: pressed, selected, loading.
- Tokens: the same color roles as `plain`. Radius `radius.control`. Padding `space.controlX` and `space.controlY`. Text style `type.body`. Error keeps what was typed.

### Text

- Used for: reading text, a screen title, and a table cell.
- States: default. Do not apply: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: body and table cell `type.body` in `theme.light.color.text`. Title `type.title`. Secondary text in `theme.light.color.textMuted`.

## Tokens

`dense.tokens.json`. Color matches `plain`. Body is 14 px. The stack is 8 px. The control radius is 2 px. The panel shadow is 0 1 px 4 px at 12 % black.
