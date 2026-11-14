<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="solution-sketch.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Facilitate a design sprint](../SKILL.md)

# Solution sketch

Source: Jake Knapp, John Zeratsky, and Braden Kowitz, *Sprint* (Simon & Schuster, 2016), Tuesday. One solution sketch is one idea, titled, self-explanatory, in three beats. It competes. It is not the screen sketch of `/uiux-sketch`, which names the blocks of one screen.

## What it fixes

One competing idea, told in three beats, before anyone picks a winner.

## What it leaves open

Which idea wins, the storyboard of the winner, the prototype, and the test.

## How to do it

1. The idea is the one the user wrote in this turn: a title and what the person does. If they gave none, write the idea as "pending." Do not invent an idea and do not mark one `accepted`.
2. For whom: the target of an accepted sprint frame, or the person named in this turn. Do not invent a name, an age, or a biography.
3. Three beats, in order: opening, action, outcome. The opening is the target moment. The action is what this idea has the person do. The outcome is what they see when the task is done.
4. A second idea is another file and another `<NNN>`. Do not supersede the first idea.
5. The file says it is not the chosen option. Do not write the decision, the wireflow, the prototype, or the test.

## Template

```markdown
# <NNN> — <title>

- State: proposed | accepted
- Chosen: no
- Source: Knapp, Zeratsky, and Kowitz, Sprint (2016), Tuesday

## Idea

## For whom

## Three beats

1. Opening —
2. Action —
3. Outcome —

## Next

The winner is chosen with `/uiux-decision`. The chosen path is `/uiux-wireflow`. This file does not choose.
```

## Example

State: `accepted`. Chosen: no. Idea: one screen that proposes tonight at 8 for two people, with confirm and change. For whom: the person booking from a phone. Opening: they look for the confirmation. Action: they confirm the proposal. Outcome: they see that the table is reserved. Next: `/uiux-decision`.

## Prerequisites

- **Idea.** Named in this turn. If it is missing, write the file, leave the idea as pending, and leave the state `proposed`. No template. Do not invent an idea. The close says no idea was invented. Regenerate with `/uiux-solution-sketch` when the idea exists.
- **Task.** An `accepted` task analysis, or the task in this turn. If neither exists, write the task analysis in this turn with template `single-task` (one task named from the request; subtasks are enter the data, confirm, see the result). That tasks file follows `understand-user`. State of the solution sketch stays the state of the idea. Change the task with `/uiux-tasks`. Regenerate this sketch with `/uiux-solution-sketch`.
- **Three beats.** In this turn, or derived when the idea was given. If the beats are missing and the idea was given, template `three-beats`: opening is the target moment of an accepted sprint frame, or the start of the task; action is what the idea's title says; outcome is that they see the result of the task. State: `accepted` when the idea came from the user and no other gap is pending. Change the beats with `/uiux-solution-sketch`. Regenerate with `/uiux-solution-sketch`.
- **For whom.** An accepted sprint frame, or the person named in this turn. If it is missing, template `role-from-task`: "the person who does <task>", with no name, age, or biography. State: `proposed`. Change it with `/uiux-solution-sketch`. Regenerate with `/uiux-solution-sketch`.

A pending idea leaves the delivery `proposed` even if other fields were filled. Template `role-from-task` also leaves it `proposed`. Template `three-beats` leaves it `accepted` only when the idea came from the user and who was already known.

## Prompts

In one message:

```text
/uiux-solution-sketch for reserving a table.
Idea: one screen that proposes tonight at 8 for two people, with confirm and change.
Task: reserve a table.
For whom: the person who books from a phone.
```

A second idea is a second message. There is no earlier command inside this piece. The frame's prompt is in [sprint-frame.md](sprint-frame.md).

## Done

- The idea is the one the user gave, or it says pending and the state is `proposed`. No idea was invented. The file says `Chosen: no`.
- When the idea was given, three beats are present. Template `three-beats` is named under Assumed when the beats were not in the message.
- Who has no invented name, age, or biography. Template `role-from-task` leaves the state `proposed`.
- The decision, the wireflow, the prototype, and the test were not written. The reply names `/uiux-decision` and does not run it.
