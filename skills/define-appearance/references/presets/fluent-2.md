<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="fluent-2.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../../README.md) / [Define the appearance](../../SKILL.md) / [Presets](../presets.md)

# Preset fluent-2

Fluent 2, web light theme.

Source: Fluent 2 design tokens and typography, https://fluent2.microsoft.design/design-tokens and https://fluent2.microsoft.design/typography. The numbers are the web light theme of Fluent UI React v9. Color: `colorBrandBackground` `#0F6CBD`, `colorBrandBackgroundHover` `#115EA3`, `colorBrandBackgroundPressed` `#0C3B5E`, `colorNeutralForeground1` `#242424`, `colorNeutralForeground2` `#424242`, `colorNeutralBackground1` `#FFFFFF`, `colorNeutralBackground3` `#F5F5F5`, `colorNeutralStroke1` `#D1D1D1`, `colorNeutralForegroundOnBrand` `#FFFFFF`, `colorStatusDangerBackground3` `#C50F1F`, `colorPaletteRedForeground1` `#BC2F32`. Type: Segoe UI, Body 1 14/20 regular, Subtitle 1 20/26 semibold. Radius: medium 4 px, extra large 8 px. Space: S 8 px, M 12 px, L 16 px, XXL 24 px. `shadow4` is two layers; the token keeps the drop layer, 0 2 px 4 px at 14 % black. Do not add the second layer as a new elevation.

Disabled colors are not in this subset. The button's disabled state is named and the delivery says the token is absent. Do not invent the gray.

- Platform: Windows, or web that follows Fluent 2
- Themes: light. Fluent also has a web dark theme. It is not in this preset.
- Native guide: Fluent 2
- Grouping: Fluent alias tokens. Button, text field, and text. Other components are added when a screen needs them.

## Recommend when

The product is Windows, or it already follows Fluent 2. Naming the platform is not naming this preset.

## Components

### Button

- Used for: the primary action.
- States: default, hover, focus, pressed. Do not apply: selected, error, loading. Disabled applies and its color token is not in this subset: say that in the delivery, do not invent the gray.
- Tokens: default fill `theme.light.color.brandBackground`, label `theme.light.color.neutralForegroundOnBrand`. Hover fill `theme.light.color.brandBackgroundHover`. Pressed fill `theme.light.color.brandBackgroundPressed`. Focus is a 2 px outline in `theme.light.color.brandBackgroundHover`. Radius `radius.medium`. Horizontal padding `space.m`, vertical padding `space.s`. Label weight semibold, size of `type.body`. Minimum height 32 px.

### Text field

- Used for: one value the person types.
- States: default, hover, focus, error. Do not apply: pressed, selected, loading. Disabled applies and its color token is not in this subset.
- Tokens: fill `theme.light.color.neutralBackground1`, text `theme.light.color.neutralForeground1`, border `theme.light.color.neutralStroke1`. Hover border `theme.light.color.neutralForeground2`. Focus outline `theme.light.color.brandBackgroundHover`. Error border `theme.light.color.danger`; the notice uses `theme.light.color.dangerForeground`; the typed value stays. Radius `radius.medium`. Text style `type.body`.

### Text

- Used for: body and a subtitle.
- States: default. Do not apply: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: body `type.body` in `theme.light.color.neutralForeground1`. Subtitle `type.subtitle` in `theme.light.color.neutralForeground1`. Secondary text in `theme.light.color.neutralForeground2`.

## Tokens

`fluent-2.tokens.json`.
