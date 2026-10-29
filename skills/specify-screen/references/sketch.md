<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="sketch.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Specify a screen](../SKILL.md)

# Sketch

Source: this plugin's fidelity order. The sketch fixes the idea. It is not the specification yet.

## What it fixes

The idea of the screen and its blocks. A block is a zone with a name (amount, form, action).

## What it leaves open

Measure, color, final copy, and style.

## How to do it

1. One SVG per screen, in grayscale (`#f4f4f4`, `#ffffff`, stroke `#222`). Rectangles and labels. No brand icons and no final typeface.
2. Draw the ideal state. Add a frame for each state that changes the blocks. The Markdown lists ideal, empty, loading, partial, error, and success, and says which do not apply.
3. The labels are the words the user already used. If a label does not exist yet, use the subtask name, not invented interface copy.
4. Do not note pixels. Do not link screens: that is the prototype.

## Markdown template

```markdown
# Sketch — <screen>

- Task or use case:
- Platform:
- States: ideal, empty, loading, partial, error, success. Do not apply: <which, and why>
- SVG: `<NNN>-sketch-<topic>-<screen>.svg`
- Left open: measure, color, final copy
```

## Example

Payment screen. Blocks of the ideal state: amount, card details, action "Pay". Error state: the same blocks plus a notice, and the card details stay filled in. Empty does not apply: the amount arrives from the order.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. If neither exists, write the task analysis in this turn with template `single-task` (one task named from the request; subtasks enter the data, confirm, see the result). State of that file: `accepted`. This sketch stays `accepted`. Change the task with `/uiux-tasks`. Regenerate this sketch with `/uiux-sketch`.

## Prompts

In one message:

```text
/uiux-sketch of the payment screen.
The task is pay with a card.
```

In order, omitting the ones already met:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

## Done

- The task or use case is named, from an accepted analysis, from this turn, or from template `single-task`. When the template was used, Assumed says so. The SVG is grayscale, one file per screen, with rectangles and labels. No brand icons, no final typeface, no pixel measures, no links to other screens.
- Ideal, empty, loading, partial, error, and success are listed. A state that does not apply says why. A state that changes the blocks has a frame. Error keeps what was typed.
- Labels are words the user already used, or the subtask name. No new interface copy.
- Left open stays measure, color, and final copy.
