# Prototype

Source: this plugin's fidelity order. The prototype is the path, not the build specification.

## What it fixes

The path of one task across screens. It opens in the browser.

## What it leaves open

Measures, annotated tokens, and accessibility requirements. Those stay in the handoff.

## How to do it

1. Start from the screens already drawn: the mock if it is `accepted`; otherwise the wireframe. Draw each screen again in its prototype SVG and add the links. Do not rewrite the mock file.
2. One SVG per screen. Link with `<a href="<file.svg>">` around the zone that is activated. The path is relative, to the sibling SVG of the same delivery. No JavaScript.
3. The first SVG is the start of the path. The Markdown says which one to open.
4. Every destination exists. If an action has no screen, do not invent the destination: ask, or leave that zone without a link and mark the delivery `proposed`.
5. Include the error state when the task can fail, as its own SVG if it is another view, or as a linked frame inside the same screen if the error does not change file. The "retry" link returns to the screen where the data is.
6. The path is not a UML diagram. If a state machine is needed, ask `adrenaline-uml-diagrams` for it.

## Markdown template

```markdown
# Prototype — <path>

- Task or use case:
- Open first: `<NNN>-prototype-<topic>-<screen>.svg`
- Visual origin: mock <N> | wireframe <N>

## Links

| Screen | Action | Destination |
| --- | --- | --- |
```

## Example

`001-prototype-pay-payment.svg` links "Pay" to `001-prototype-pay-result.svg`. "Retry" on the error result returns to `001-prototype-pay-payment.svg`. The payment SVG is opened in the browser.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. Stops the delivery. Earlier command: `/uiux-tasks`.
- **Path.** An `accepted` user flow, or the path in this turn. Stops the delivery. Earlier command: `/uiux-user-flow`.
- **Drawn screen.** An `accepted` mock, or an `accepted` wireframe, or the screen's blocks in this turn. Stops the delivery. Earlier command: `/uiux-wireframe` or `/uiux-mock`.

## Prompts

In one message:

```text
/uiux-prototype of payment.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
Payment screen: amount, card, and a Pay button. No UI kit: do the wireframe first in this turn.
If it should look like the mock, include the kit.
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
/uiux-wireframe of the payment screen.
The task is pay with a card.
Platform: web.
```

```text
/uiux-prototype of payment.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```
