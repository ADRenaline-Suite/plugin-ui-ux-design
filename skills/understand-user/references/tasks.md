<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="tasks.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Understand the user](../SKILL.md)

# User tasks

Source: Nielsen Norman Group, Task Analysis. The goal, if it comes from a use case, is the one from `plugin-project-manager`.

## What it fixes

The person's goal, the tasks, the subtasks, and the order they happen in. Each task is something the person completes. A subtask is a step of that task.

## What it leaves open

Screens, visual appearance, final copy, and metrics.

## How to do it

1. Write the goal in the user's words or the use case's words. If the goal does not fit in one sentence, ask them to narrow it. If no goal is stated, apply template `single-task`.
2. List the tasks in the order the person does them. Number them.
3. Under each task, list the subtasks. Do not add a task the user did not describe and the goal does not require. Template `single-task` is the exception: it adds the three subtasks below.
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

- **Goal.** Stated by whoever asks for the analysis, in this turn. If it is missing, template `single-task`: one task named from the noun or the verb in the request; subtasks enter the data, confirm, see the result; each depends on the previous one, and the first depends on none. Origin: `template single-task`. State: `accepted`. Change it with `/uiux-tasks`. Regenerate with `/uiux-tasks`.

## Prompts

In one message:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

There is no earlier command. The single prompt is the way.

## Done

- The goal is one sentence. Origin is the use case, the conversation, or template `single-task`. When the template was used, Assumed says so.
- Tasks are numbered and in order. Each one has subtasks and Depends on. No task was added that the user did not describe and the goal does not require, except the three subtasks of template `single-task`.
- Screens, visual appearance, final copy, metrics, and a persona are absent.
- The source line cites Nielsen Norman Group, Task Analysis.
