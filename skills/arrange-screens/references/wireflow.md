# Wireflow

Source: the user flow of the same task, drawn with a wireframe at each step. It is still UX, not UML.

## What it fixes

The same path, with the hierarchy of each step in view.

## What it leaves open

Color, type, and build measures.

## How to do it

1. If there is an `accepted` user flow for that task, follow its screens and its returns. If there is none and the user describes the path in this turn, use it and cite it. If the path is not stated, follow "When a prerequisite is missing" in the skill.
2. One SVG per screen, in gray, with the same visual rule as a wireframe: blocks, labels, no brand color. `xmlns="http://www.w3.org/2000/svg"`, `viewBox`, no scripts and no `foreignObject`.
3. The Markdown orders the steps and points at each SVG. The SVGs do not have to be linked: the link between screens is the prototype. Here the order comes from the list.
4. Include the error step when the flow has one. The error frame keeps the data the person typed.
5. Each step names the task it covers.

## Template

```markdown
# Wireflow — <task>

- Task or use case:
- Origin user flow: <file> | described in this turn

## Steps

| Step | Screen | SVG |
| --- | --- | --- |
| 1 | Payment details | `<NNN>-wireflow-<topic>-details.svg` |
```

## Example

Three gray SVGs: details, result, and error. The error one shows the notice and the card fields still filled. The Markdown numbers them in the user flow's order.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. Stops the delivery. Earlier command: `/uiux-tasks`.
- **Path.** An `accepted` user flow, or the path in this turn. Stops the delivery. Earlier command: `/uiux-user-flow`.

## Prompts

In one message:

```text
/uiux-wireflow for pay with a card.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
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
