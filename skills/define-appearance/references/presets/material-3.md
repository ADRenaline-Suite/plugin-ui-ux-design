<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="material-3.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../../README.md) / [Define the appearance](../../SKILL.md) / [Presets](../presets.md)

# Preset material-3

Material Design 3 static baseline, light theme. The values below are that baseline. Do not recolor them.

Source: Material Design 3. Color roles and the static baseline, https://m3.material.io/styles/color/roles and https://m3.material.io/styles/color/static/baseline. The baseline light roles used here are primary `#6750A4`, onPrimary `#FFFFFF`, surface `#FEF7FF`, onSurface `#1D1B20`, error `#B3261E`, outline `#79747E`. Type scale: body large 16/24, title large 22/28 medium, label large 14/20 medium, Roboto, as published for Material 3. Corner scale: extra small 4 dp, medium 12 dp, large increased 20 dp, https://m3.material.io/styles/shape/corner-radius-scale. Elevation levels, not a drop shadow: a filled button rests at level 0 and an elevated card at level 1 (1 dp), https://m3.material.io/styles/elevation/tokens. State layers on a filled button: hover 8 %, focus 12 %, pressed 12 % of onPrimary. Disabled container is onSurface at 12 % and the label is onSurface at 38 %.

The shadow token is one layer for level 1 when a shadow has to be drawn (offset 0 1 px, blur 3 px, 12 % black). Material 3's own rule is the level, not this shadow. The file says so. Do not add a second shadow at delivery.

- Platform: Android, or web that follows Material Design 3
- Themes: light. The baseline also has a dark scheme. It is not in this preset. Add it only when the product has dark, as another delivery.
- Native guide: Material Design 3
- Grouping: Material color roles. Button, text field, and text. Other components are added when a screen needs them.

## Recommend when

The product is Android, or it already follows Material Design 3. Naming the platform is not naming this preset.

## Components

### Button

- Used for: the filled primary action.
- States: default, hover, focus, pressed, disabled. Do not apply: selected, error, loading.
- Tokens: default fill `theme.light.color.primary`, label `theme.light.color.onPrimary`, elevation `elevation.level0`. Hover, focus, and pressed keep that fill and add the state layer described in the source (8 %, 12 %, 12 %). Disabled uses `theme.light.color.onSurface` at 12 % for the fill and at 38 % for the label. Radius `radius.button` (20 dp, the large-increased step). A stadium ("full") is half the shorter side when the height is known; do not invent another radius. Padding follows `space.16` horizontal and `space.8` vertical. Label style `type.label`.

### Text field

- Used for: an outlined field.
- States: default, hover, focus, disabled, error. Do not apply: pressed, selected, loading.
- Tokens: text `theme.light.color.onSurface`, container `theme.light.color.surface`. Default outline `theme.light.color.outline`. Hover outline `theme.light.color.onSurface`. Focus outline `theme.light.color.primary`. Error outline `theme.light.color.error`; the typed value stays. Disabled outline is `theme.light.color.onSurface` at 12 %. Radius `radius.extraSmall`. Text style `type.body`.

### Text

- Used for: body and the screen title.
- States: default. Do not apply: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: body `type.body` in `theme.light.color.onSurface`. Title `type.title` in `theme.light.color.onSurface`. Secondary text `type.body` in `theme.light.color.onSurfaceVariant`.

## Tokens

`material-3.tokens.json`. Space is the 4 dp increment (4, 8, 16, 24).
