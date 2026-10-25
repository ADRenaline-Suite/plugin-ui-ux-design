# Heuristics

Source: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, and Severity Ratings for Usability Problems.

## What it fixes

Each usability problem visible on the screen: the heuristic, the place, the severity, and the correction.

## Severity

| Value | Meaning |
| --- | --- |
| 0 | Not a usability problem |
| 1 | Cosmetic |
| 2 | Minor |
| 3 | Major |
| 4 | Catastrophe: it blocks the task |

## Heuristics

Use the Nielsen Norman Group name and, in parentheses, a gloss in the language of the artifact.

1. Visibility of system status
2. Match between system and the real world
3. User control and freedom
4. Consistency and standards
5. Error prevention
6. Recognition rather than recall
7. Flexibility and efficiency of use
8. Aesthetic and minimalist design
9. Help users recognize, diagnose, and recover from errors
10. Help and documentation

## How to do it

1. Walk the states of the screen, not only the ideal one. An error that clears what was typed is a finding.
2. One finding, one heuristic. If it fits two, choose the one that explains the correction.
3. The correction says what changes on the screen. Do not write the code.
4. Close by asking `adrenaline-accessibility` for the review. Do not assign a WCAG criterion.

## Template

```markdown
# Heuristics — <screen>

- What was reviewed: <file or description>
- Source: Nielsen Norman Group, 10 heuristics and severity 0–4.

| # | Heuristic | Screen | State | Severity | Finding | Correction |
| --- | --- | --- | --- | --- | --- | --- |

Accessibility: ask `adrenaline-accessibility` for the review.
```

## Example

Screen: payment. State: network error. Heuristic: Visibility of system status. Severity: 3. Finding: the button still says "Pay" and there is no message. Correction: an error message and a retry action; keep the card data.

## Prerequisites

- **Screen or flow.** An `accepted` file, or what is described in this turn. Stops the delivery. Earlier command: `/uiux-mock`.

## Prompts

In one message:

```text
/uiux-heuristics of payment on a network error.
The screen shows the Pay button with no message and keeps the card data.
```

In order, omitting the ones already met:

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit, light theme: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```
