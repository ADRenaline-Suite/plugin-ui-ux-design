# Wireframe

Source: this plugin's fidelity order. Breakpoints: the product's, or Material Design 3 if the product has none.

## What it fixes

The hierarchy and the layout of one screen, per breakpoint. What comes first, what stacks, and what splits into columns.

## What it leaves open

Visual style: brand color, final typeface, elevation.

## How to do it

1. Grayscale, the same as the sketch. This time the blocks have hierarchy: a title, the content, the primary action. The reading order is top to bottom and, in left-to-right languages, left to right.
2. The Markdown describes the layout of each breakpoint. The SVG redraws a breakpoint only when the layout changes.
3. Include a long string in at least one block, to see the line break. If a short string may be translated, reserve room for 200–300% (W3C Internationalization, Text size in translation). If the product needs RTL, one frame with `direction="rtl"` on the SVG group.
4. List the states. Draw the ones that change the layout, especially error, which keeps what was typed.
5. Still no brand color and no build measures. Measures belong to the handoff.

## Markdown template

```markdown
# Wireframe — <screen>

- Task or use case:
- Platform:
- Breakpoints: <the product's, or Material Design 3>
- States, and which change the layout:
- Long test string:
- Expansion on translation:
- RTL: yes, in the frame <name> | does not apply
- SVG: `<NNN>-wireframe-<topic>-<screen>.svg`

## Layout per breakpoint

| Breakpoint | Layout |
| --- | --- |
```

## Example

Payment, web, Material Design 3. Compact: amount, form, and "Pay" in one column. Expanded: summary on the left and form on the right. Error adds the notice above the form and does not clear the card number. Large and extra-large only widen the expanded layout; the Markdown says so and the SVG does not repeat them.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. Stops the delivery. Earlier command: `/uiux-tasks`.

## Prompts

In one message:

```text
/uiux-wireframe of the payment screen.
The task is pay with a card.
Platform: web.
```

In order, omitting the ones already met:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```
