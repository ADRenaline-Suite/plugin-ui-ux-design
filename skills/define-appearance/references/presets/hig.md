[🏠 UI/UX Design](../../../../README.md) / [Define the appearance](../../SKILL.md) / [Presets](../presets.md)

# Preset hig

Apple Human Interface Guidelines, light appearance, for iOS, iPadOS, and macOS.

Source: Human Interface Guidelines, color, typography, and layout, https://developer.apple.com/design/human-interface-guidelines/color, https://developer.apple.com/design/human-interface-guidelines/typography, and https://developer.apple.com/design/human-interface-guidelines/layout. The type styles at the Large Dynamic Type size are Large Title 34 pt regular, Title 1 28 pt regular, Headline 17 pt semibold, Body 17 pt regular. SF Pro is the system face.

The HIG does not publish hex for the system colors. The hex in the token file is the light sRGB appearance of the named colors: systemBlue `#007AFF`, systemRed `#FF3B30`, label `#000000`, secondaryLabel `rgb(60, 60, 67)` at 60 % opacity, systemBackground `#FFFFFF`, secondarySystemBackground `#F2F2F7`, separator `rgb(60, 60, 67)` at 29 % opacity. Do not replace them with another blue.

The HIG does not publish one corner token, one shadow token, or a line-height token next to the text styles. `radius.grouped` (10 px) is a working continuous corner for an inset group, and `elevation.card` is a stand-in so the kit has an elevation token (0 1 px 3 px at 12 % black). Depth in the HIG is a material, not this shadow. `space.unit` (8 px) is a working step. `space.margin` (16 px) is the common iPhone layout margin. Body line height in the file is 22 pt (multiplier 1.29). Do not present the working values as Apple tokens, and do not change them at delivery.

- Platform: iOS, iPadOS, or macOS
- Themes: light. The named colors also adapt to dark. Dark is not in this preset.
- Native guide: Apple Human Interface Guidelines
- Grouping: the preset's. Button, text field, and text. Other components are added when a screen needs them.

## Recommend when

The product is iOS, iPadOS, or macOS. Naming the platform is not naming this preset.

## Components

### Button

- Used for: the prominent action.
- States: default, hover, focus, pressed, disabled. Do not apply: selected, error, loading.
- Tokens: fill `theme.light.color.systemBlue`, label `theme.light.color.systemBackground`. Pressed and hover keep that tint; the platform draws the pressed appearance. Hover applies on a pointer. Focus follows the platform focus ring. Disabled keeps the same colors at reduced emphasis; this subset has no second hex for it. Minimum control size is 44 px. Radius `radius.grouped`. Label style `type.headline`.

### Text field

- Used for: one value the person types.
- States: default, focus, disabled, error. Do not apply: hover, pressed, selected, loading. Hover does not apply to the field on touch.
- Tokens: fill `theme.light.color.secondarySystemBackground`, text `theme.light.color.label`, placeholder `theme.light.color.secondaryLabel`. Focus keeps the fill and uses `theme.light.color.systemBlue` for the cursor. Error uses `theme.light.color.systemRed`; the typed value stays. Radius `radius.grouped`. Text style `type.body`.

### Text

- Used for: body, a title, and a large title.
- States: default. Do not apply: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: body `type.body` in `theme.light.color.label`. Title `type.title`. Large title `type.largeTitle`. Secondary text in `theme.light.color.secondaryLabel`.

## Tokens

`hig.tokens.json`.
