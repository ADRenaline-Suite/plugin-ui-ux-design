[🏠 UI/UX Design](../../../../README.md) / [Define the appearance](../../SKILL.md) / [Presets](../presets.md)

# Preset plain

Default starter for a web product with no brand. Comfortable reading. No external standard: these values belong to this plugin.

- Platform: web
- Themes: light
- Native guide: none
- Grouping: the preset's. Button, text field, and text. Other components are added when a screen needs them.

## Recommend when

Web, no brand, and nobody has chosen a preset. If none is selected, this is the one that is written.

## Components

### Button

- Used for: the primary action of the screen.
- States: default, hover, focus, pressed, disabled. Do not apply: selected, error, loading.
- Tokens: default fill `theme.light.color.action`, label `theme.light.color.onAction`. Hover fill `theme.light.color.actionHover`. Pressed fill `theme.light.color.actionPressed`. Focus uses the same fill as default and a 2 px outline in `theme.light.color.action`. Disabled fill `theme.light.color.disabled`, label `theme.light.color.onDisabled`. Radius `radius.control`. Horizontal padding `space.controlX`, vertical padding `space.controlY`. Label style `type.label`.

### Text field

- Used for: one value the person types.
- States: default, hover, focus, disabled, error. Do not apply: pressed, selected, loading.
- Tokens: fill `theme.light.color.background`, text `theme.light.color.text`, border `theme.light.color.border`. Hover and focus use a 2 px border in `theme.light.color.action`. Error border and the error notice use `theme.light.color.error`; the typed value stays. Disabled fill `theme.light.color.disabled`, text `theme.light.color.onDisabled`. Radius `radius.control`. Padding `space.controlX` and `space.controlY`. Text style `type.body`.

### Text

- Used for: reading text and the screen title.
- States: default. Do not apply: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: body `type.body` in `theme.light.color.text`. Title `type.title` in `theme.light.color.text`. Secondary text `type.body` in `theme.light.color.textMuted`.

## Tokens

`plain.tokens.json`. Color, type, space, radius, and elevation. Space steps are 8, 16, and 32. Radius of a control is 4 px. The panel shadow is 0 2 px 8 px at 12 % black.
