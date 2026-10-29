<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="prototype.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Specify a screen](../SKILL.md)

# Prototype

Source: this plugin's fidelity order. The prototype is the path, not the build specification.

## What it fixes

The path of one task across screens. It opens in the browser.

## What it leaves open

Measures, annotated tokens, and accessibility requirements. Those stay in the handoff.

## How to do it

1. Start from the screens already drawn: the mock if it is `accepted`; otherwise the wireframe. If neither exists and this turn does not bring the blocks, write a wireframe in this turn with template `task-blocks` (one block per subtask, plus the primary action). Draw each screen again in its prototype SVG and add the links. Do not rewrite an existing mock file.
2. One SVG per screen. Link with `<a href="<file.svg>">` around the zone that is activated. The path is relative, to the sibling SVG of the same delivery. No JavaScript.
3. The first SVG is the start of the path. The Markdown says which one to open.
4. Every destination exists. If an action has no screen, leave that zone without a link and mark the delivery `proposed`. Do not invent the destination.
5. Include the error state when the task can fail, as its own SVG if it is another view, or as a linked frame inside the same screen if the error does not change file. The "retry" link returns to the screen where the data is.
6. The path is not a UML diagram. If a state machine is needed, ask `plugin-uml-diagrams` for it.

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

- **Task.** An `accepted` task analysis, or the task in this turn. If neither exists, write it with template `single-task`. State: `accepted`. Change it with `/uiux-tasks`. Regenerate this prototype with `/uiux-prototype`.
- **Path.** An `accepted` user flow, or the path in this turn. If neither exists, write it with template `linear-three` (same screen rules as the mock). State: `accepted`. Change it with `/uiux-user-flow`. Regenerate this prototype with `/uiux-prototype`.
- **Drawn screen.** An `accepted` mock, or an `accepted` wireframe, or the screen's blocks in this turn. If none of these exist, write a wireframe in this turn with template `task-blocks`: one block per subtask of the task, plus the primary action. State: `accepted`. Change it with `/uiux-wireframe` or `/uiux-mock`. Regenerate this prototype with `/uiux-prototype`.

## Prompts

In one message:

```text
/uiux-prototype of payment.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
Payment screen: amount, card, and a Pay button. No UI kit: do the wireframe first in this turn.
If it should look like the mock, include the kit.
UI kit: preset plain. Other presets: dense, material-3, hig, fluent-2.
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

## Done

- The path opens in the browser. Each screen is its own SVG. Links are `<a href>` to a sibling SVG of this same `<NNN>`. There is no JavaScript. A wireframe written in this turn from template `task-blocks` is named under Assumed.
- The Markdown names the file to open first. Every linked destination exists. A zone with no destination is unlinked and the delivery is `proposed`.
- The error of a task that can fail is included, and retry returns to the screen that holds the data.
- Measures, tokens, and accessibility notes are absent. It is not a UML diagram. The mock or wireframe file was not rewritten.
