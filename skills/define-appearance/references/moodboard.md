[🏠 UI/UX Design](../../../README.md) / [Define the appearance](../SKILL.md)

# Moodboard

The moodboard has no single standard in this plugin's sources. It records the visual direction so it can be repeated in the UI kit and in the mocks.

## What it fixes

References (links the user gave), color, type, and tone, applied to sample screens.

## What it leaves open

Formal tokens and the states of each component. That is the UI kit.

## How to do it

1. The references are links or pieces the user provided. Do not search a gallery or invent other brands as if they belonged to the product. If none are provided, apply template `neutral` and leave the delivery `proposed`.
2. One SVG per sample screen. Color swatches in rectangles with their hex, one line of type in the family the user named, and a screen block in that tone. `xmlns="http://www.w3.org/2000/svg"` and `viewBox`. No `foreignObject`.
3. Tone is said with yes and no examples the user gave. If they gave none, describe the tone in one sentence and do not write the microcopy: that is `plugin-ux-writing`.
4. If the product already has a UI kit, the moodboard does not replace it. It shows how the kit is applied.

## Template

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

## Example

Direction "light shop". Reference: the guide the user passed. Color swatch `#0066cc` on background `#ffffff`, one line in the family they named, and a payment block with that accent. The SVG is the sample, not the handoff.

## Prerequisites

- **Visual references.** Links or pieces provided by whoever asks for the moodboard. A gallery is not searched. If none arrive, template `neutral`: grayscale (`#f4f4f4`, `#ffffff`, stroke `#222`), `font-family="system-ui, Segoe UI, sans-serif"`, tone "clear and direct", and the references line says none were provided. State: `proposed`. Change it with `/uiux-moodboard`. Regenerate with `/uiux-moodboard`.

## Prompts

In one message:

```text
/uiux-moodboard of the shop.
Reference: <url or piece you paste>.
Light theme, accent #0066cc, background #ffffff, type Source Sans 3.
```

There is no earlier command. The single prompt is the way.

## Done

- References are links or pieces the user provided, or template `neutral` when none were provided. No gallery was searched and no other brand was added as if it were the product's. When `neutral` was used, the delivery is `proposed` and Assumed says so.
- Each sample screen has an SVG with `xmlns` and a `viewBox`, a color swatch with its hex, and the type the user named. No `foreignObject`.
- Tone uses the user's yes and no examples, or one sentence if they gave none. Microcopy was not written. Tokens and component states are left open. An existing kit was not replaced.
