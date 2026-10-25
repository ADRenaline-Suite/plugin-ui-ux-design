# User tasks

Source: Nielsen Norman Group, Task Analysis. The goal, if it comes from a use case, is the one from `adrenaline-project-manager`.

## What it fixes

The person's goal, the tasks, the subtasks, and the order they happen in. Each task is something the person completes. A subtask is a step of that task.

## What it leaves open

Screens, visual appearance, final copy, and metrics.

## How to do it

1. Write the goal in the user's words or the use case's words. If the goal does not fit in one sentence, ask them to narrow it.
2. List the tasks in the order the person does them. Number them.
3. Under each task, list the subtasks. Do not add a task the user did not describe and the goal does not require.
4. Mark which task depends on another.
5. Each task that will later have a screen must be citable by its name. Use those names as given in later deliveries.

## Template

```markdown
# Tasks — <topic>

- Goal:
- Origin: use case <name> | goal stated in the conversation
- Source: Nielsen Norman Group, Task Analysis. ISO 9241-210:2019, context of use.

## Tasks

1. <task>
   - Subtasks:
   - Depends on:
```

## Example

Goal: pay an order with a card.

1. Review the amount — subtasks: see the total, see the breakdown. Depends on: none.
2. Enter the card — subtasks: number, expiry, code. Depends on: 1.
3. Confirm the payment — subtasks: accept the charge, see the result. Depends on: 2.

## Prerequisites

- **Goal.** Stated by whoever asks for the analysis, in this turn. Stops the delivery. No earlier command.

## Prompts

In one message:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

There is no earlier command. The single prompt is the way.
