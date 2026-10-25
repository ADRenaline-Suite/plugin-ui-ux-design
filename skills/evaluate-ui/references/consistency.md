# Consistency with the UI kit

Source: the product's `accepted` UI kit. There is no other standard. If there is no `accepted` kit and no tokens in this turn, follow "When a prerequisite is missing" in the skill. Do not compare against a kit invented in this turn.

## What it fixes

Each place a screen drifts from the kit's components and tokens.

## How to do it

1. Name the kit file. Check color, type, space, radius, elevation, and the component states (default, hover, focus, pressed, disabled, selected, error, loading).
2. A drift says which token or component, on which screen and state, what is seen instead, and how to return to the kit.
3. If the drift is intentional, do not file it as accepted. Ask for a decision from `record-decision` and leave this finding waiting on that decision.
4. This does not replace the heuristics or WCAG.

## Template

```markdown
# Consistency — <screen>

- UI kit:
- Screen reviewed:

| Component or token | Screen | State | What differs | Correction |
| --- | --- | --- | --- | --- |
```

## Example

The "Pay" button uses a blue that is not in `color.action`. Correction: use the kit token `color.action`. If the team wants that other blue, it is recorded as a decision and the kit changes in another delivery.

## Prerequisites

- **UI kit.** An `accepted` kit, or the tokens in this turn. If they arrive in this turn, write the kit with `define-appearance` before comparing. Stops the delivery. Earlier command: `/uiux-ui-kit`.
- **Screen.** An `accepted` file, or the screen described in this turn. Stops the delivery. Earlier command: `/uiux-mock`.

## Prompts

In one message:

```text
/uiux-consistency of the payment screen.
Screen: the accepted mock, or describe it here.
UI kit, light theme: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

In order, omitting the ones already met:

```text
/uiux-ui-kit for the shop. Web platform, light theme.
Action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```
