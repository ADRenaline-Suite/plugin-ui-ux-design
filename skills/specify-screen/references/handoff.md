# Handoff

Source: this plugin's practice. There is no single handoff standard. It is enough to build the screen without guessing: measures, states, copy, behavior per breakpoint, and accessibility notes. The implementation review uses this delivery as the criterion, together with the UI kit.

## What it fixes

Everything the person building the screen would otherwise have to guess.

## What it leaves open

Nothing about the screen. The code stays outside this plugin.

## How to do it

1. Start from the `accepted` mock. The handoff SVG is that mock with redlines: dimension lines (dashed stroke) and the measured value. The unit is the UI kit's (`px` or `rem` in the tokens). Do not invent a measure the kit does not have: if it is missing, note it as a gap and leave the delivery `proposed`.
2. The Markdown describes the behavior per breakpoint: what is shown, what stacks, what moves. Repeat a frame in the SVG only when the layout changes.
3. Copy: ask `adrenaline-ux-writing` for it (microcopy, errors, empty, loading, success, confirmations). If the user already pasted it, use it and cite the origin. Do not write it here. If it is missing, the delivery stays `proposed` and lists the gaps.
4. Accessibility notes: ask `adrenaline-accessibility` for them (focus order, headings, landmarks, accessible names, alternative text). Include them as given, each with the WCAG criterion that plugin named. Do not run the audit. If they are missing, the delivery stays `proposed`.
5. States: ideal, empty, loading, partial, error, and success; no permission and offline when they apply. On error, what was typed is kept. Each state says what is visible and what the primary action does.
6. Content check: a long string and the expansion on translation. RTL if the product needs it. The translation itself stays out of scope.
7. The product's themes, with the tokens of each one.

## Markdown template

```markdown
# Handoff — <screen>

- Task or use case:
- UI kit:
- Origin mock:
- Platform and breakpoints:
- Themes:
- SVG with redlines: `<NNN>-handoff-<topic>-<screen>.svg`
- Origin of the copy:
- Origin of the accessibility notes:
- State of this delivery: accepted | proposed (missing: )

## Behavior per breakpoint

| Breakpoint | What changes |
| --- | --- |

## States

| State | What is visible | Primary action | Keeps what was typed |
| --- | --- | --- | --- |

## Copy

| Element | Copy | Origin |
| --- | --- | --- |

## Accessibility

| Note | Element | Criterion |
| --- | --- | --- |

## Measures

| Element | Measure | Token |
| --- | --- | --- |
```

## Example

Payment handoff. The dimension between the amount and the form is the token `space.stack`. Error shows the copy `adrenaline-ux-writing` gave and does not clear the card. The focus order is the one `adrenaline-accessibility` noted. If that plugin is not in the session, the note is asked of the user and, until it arrives, the `STATUS.md` row stays `proposed`.

## Prerequisites

- **Mock.** An `accepted` mock. If this turn brings the task, the path, and the tokens, write the kit and the mock before the handoff. Stops the delivery. Earlier command: `/uiux-mock`.
- **UI kit.** An `accepted` kit, or the tokens in this turn. Without a measure from the kit, that dimension stays a gap. Stops the delivery. Earlier command: `/uiux-ui-kit`.
- **Copy.** Pasted by whoever asks for the handoff, or given by `adrenaline-ux-writing`. Does not stop the delivery: the delivery stays `proposed`. No earlier command.
- **Accessibility notes.** Pasted by whoever asks for the handoff, or given by `adrenaline-accessibility`. Does not stop the delivery: the delivery stays `proposed`. No earlier command.

## Prompts

In one message:

```text
/uiux-handoff of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit, light theme: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
Copy: paste it here, or it is asked of adrenaline-ux-writing and the handoff stays proposed.
Accessibility notes: paste them here, or they are asked of adrenaline-accessibility and the handoff stays proposed.
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

```text
/uiux-handoff of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```
