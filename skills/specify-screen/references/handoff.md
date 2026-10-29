<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="handoff.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Specify a screen](../SKILL.md)

# Handoff

Source: this plugin's practice. There is no single handoff standard. It is enough to build the screen without guessing: measures, states, copy, behavior per breakpoint, and accessibility notes. The implementation review uses this delivery as the criterion, together with the UI kit.

## What it fixes

Everything the person building the screen would otherwise have to guess.

## What it leaves open

Nothing about the screen. The code stays outside this plugin.

## How to do it

1. Start from the `accepted` mock. If there is none, write the task (`single-task` if needed), the user flow (`linear-three` if needed), the kit (preset `plain` if none is selected), and the mock in this turn, then the handoff. The handoff stays `proposed` when that mock was assumed. The handoff SVG is the mock with redlines: dimension lines (dashed stroke) and the measured value. The unit is the UI kit's (`px` or `rem` in the tokens). Do not invent a measure the kit does not have: if it is missing, note it as a gap and leave the delivery `proposed`.
2. The Markdown describes the behavior per breakpoint: what is shown, what stacks, what moves. Repeat a frame in the SVG only when the layout changes.
3. Copy: ask `plugin-ux-writing` for it (microcopy, errors, empty, loading, success, confirmations). If the user already pasted it, use it and cite the origin. Do not write it here. If it is missing, the delivery stays `proposed` and lists the gaps.
4. Accessibility notes: ask `plugin-accessibility` for them (focus order, headings, landmarks, accessible names, alternative text). Include them as given, each with the WCAG criterion that plugin named. Do not run the audit. If they are missing, the delivery stays `proposed`.
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

Payment handoff. The dimension between the amount and the form is the token `space.stack`. Error shows the copy `plugin-ux-writing` gave and does not clear the card. The focus order is the one `plugin-accessibility` noted. If that plugin is not in the session, the note is asked of the user and, until it arrives, the `STATUS.md` row stays `proposed`.

## Prerequisites

- **Mock.** An `accepted` mock, or one written in this turn. If it is missing, write the task, the path, the kit, and the mock first. The task is template `single-task` when none is stated. The path is template `linear-three` when none is stated. The kit is the accepted one, the named preset, the tokens in this turn, or preset `plain`. State of this handoff: `proposed` when that mock was assumed in this turn, and also when copy or notes are missing. Change the mock with `/uiux-mock`. Regenerate this handoff with `/uiux-handoff`.
- **UI kit.** An `accepted` kit, a named preset, or the tokens in this turn. If none of these arrive, write preset `plain` with `define-appearance` before the handoff. A measure the kit does not have stays a gap. State: `accepted` for the kit. Change it with `/uiux-ui-kit`. Regenerate this handoff with `/uiux-handoff`.
- **Copy.** Pasted by whoever asks for the handoff, or given by `plugin-ux-writing`. No template. The cell stays blank. The delivery stays `proposed`. Nothing was invented. Paste the copy and regenerate with `/uiux-handoff`.
- **Accessibility notes.** Pasted by whoever asks for the handoff, or given by `plugin-accessibility`. No template. The cell stays blank. The delivery stays `proposed`. Nothing was invented. Paste the notes and regenerate with `/uiux-handoff`.

## Prompts

In one message:

```text
/uiux-handoff of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit: preset plain. Other presets: dense, material-3, hig, fluent-2.
Copy: paste it here, or it is asked of plugin-ux-writing and the handoff stays proposed.
Accessibility notes: paste them here, or they are asked of plugin-accessibility and the handoff stays proposed.
```

The UI kit is not in this order. When it is missing, preset `plain` is written with the handoff.

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
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

```text
/uiux-handoff of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

## Done

- The SVG is the accepted mock plus redlines. Every measure is a token the kit has. A missing measure is a gap, and the delivery is `proposed`.
- Behavior per breakpoint, states, copy, accessibility, and measures tables are present. Error keeps what was typed. A state that does not apply says why.
- Copy and accessibility notes are cited from the user, `plugin-ux-writing`, or `plugin-accessibility`. If either is missing, the cell stays blank, the delivery is `proposed`, and the gaps are listed. They were not written here and WCAG was not audited. A mock assumed in this turn also leaves the handoff `proposed`, and Assumed names the templates.
- Long-string and translation-expansion checks are in the file. RTL is included only if the product needs it. No HTML.
