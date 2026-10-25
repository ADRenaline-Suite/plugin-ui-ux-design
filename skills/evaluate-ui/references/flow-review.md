# Flow review

It has no standard other than this plugin's sources. The criterion is the task: extra steps, dead ends, and missing states.

## What it fixes

Problems of the path, not of the appearance or of the code.

## How to do it

1. Read the `accepted` user flow or wireflow. If the user describes the path in this turn, use that description.
2. An extra step is one that does not move the task forward. A dead end is a screen with no exit toward success or toward recovery. A missing state is one from the list (ideal, empty, loading, partial, error, success, and, when they apply, no permission and offline) that the path does not cover.
3. Error has to be able to return to the data that was typed.
4. Each finding names the screen and the correction of the path. Do not redraw the flow here: if the correction is accepted, it is updated with `arrange-screens`.
5. Ask `adrenaline-accessibility` for the review. Do not audit WCAG. Do not verify the use case.

## Template

```markdown
# Flow review — <task>

- Flow reviewed:
- Source: this plugin's criterion (extra steps, dead ends, missing states).

| Kind | Screen | Finding | Correction |
| --- | --- | --- | --- |

Accessibility: ask `adrenaline-accessibility` for the review.
```

## Example

Kind: dead end. Screen: payment error. Finding: there is no action to return to the data. Correction: a return to the card screen, which keeps what was typed. Kind: missing state. The charge's loading state does not appear on the path.

## Prerequisites

- **Path.** An `accepted` user flow, or the path in this turn. Stops the delivery. Earlier command: `/uiux-user-flow`.

## Prompts

In one message:

```text
/uiux-flow-review of pay with a card.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

In order, omitting the ones already met:

```text
/uiux-user-flow for pay with a card.
The task is pay with a card.
Screens: cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```
