# Mock

Source: the product's UI kit. Tokens written in this turn follow the Design Tokens Format Module 2025.10; the token file is produced by `define-appearance`, not by this manual. Breakpoints: the product's, or Material Design 3.

## What it fixes

The visual appearance of one screen, with the UI kit tokens and per theme.

## What it leaves open

The path to other screens and the build specification (annotated measures, behavior, accessibility). That is the prototype and the handoff.

## How to do it

1. The path has to be decided: an `accepted` user flow, or the path in this turn. If it is not, follow "When a prerequisite is missing" in the skill.
2. Use the tokens of the `accepted` UI kit, or the ones that arrive in this turn. Color, type, space, radius, and elevation come from there. If they arrive in this turn and there is no kit, write the kit with `define-appearance` and then the mock. If there is neither a kit nor tokens, follow "When a prerequisite is missing" in the skill. Do not invent a palette.
3. One frame per theme in the ideal state (light, dark, brand variant), only the themes the product has. Do not add dark mode if the product does not have it.
4. Real copy, from the user or from `adrenaline-ux-writing`. If the final copy is missing, use the labels already agreed and say so in the Markdown; do not write new microcopy.
5. Draw the states that change the appearance. Error keeps what was typed and shows what failed.
6. The SVG uses the kit colors in `fill` and `stroke`. Still no redlines: the dimensions belong to the handoff.

## Markdown template

```markdown
# Mock — <screen>

- Task or use case:
- Path decided: <user flow file, or "described in this turn">
- UI kit: <accepted file> | tokens from this turn
- Themes:
- Platform and breakpoints:
- States drawn:
- Origin of the copy: user | adrenaline-ux-writing | agreed labels, final copy still missing
- SVG: `<NNN>-mock-<topic>-<screen>.svg`
```

## Example

Mock of payment in the light theme, with the shop kit's action color and type. The error state uses the kit's error color, the notice "The charge did not go through" if `adrenaline-ux-writing` already gave it, and the card fields stay filled. The path to the result is in the accepted user flow; this mock does not link it.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. Stops the delivery. Earlier command: `/uiux-tasks`.
- **Path.** An `accepted` user flow, or the path in this turn. Stops the delivery. Earlier command: `/uiux-user-flow`.
- **UI kit.** An `accepted` kit, or the tokens in this turn. If they arrive in this turn and there is no kit, write the kit with `define-appearance` and then the mock. Stops the delivery. Earlier command: `/uiux-ui-kit`.

## Prompts

In one message:

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit, light theme: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

In order, omitting the ones already met:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

```text
/uiux-user-flow for pay with a card.
The task is pay with a card.
Screens: cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

```text
/uiux-ui-kit for the shop. Web platform, light theme.
Action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```
