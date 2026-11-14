<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="sprint-frame.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Facilitate a design sprint](../SKILL.md)

# Sprint frame

Source: Jake Knapp, John Zeratsky, and Braden Kowitz, *Sprint* (Simon & Schuster, 2016), Monday. The long-term goal is the optimistic outcome the team would celebrate. The sprint questions are the risks that could sink the week, written as questions. The target is one customer and one moment on the map, the moment the prototype will cover.

## What it fixes

The bet for this week: the long-term goal, the questions the week must answer, and the target moment. It does not choose a solution.

## What it leaves open

The competing ideas, the decision, the storyboard, the prototype, and the test.

## How to do it

1. Long-term goal: one sentence, set in the future, about the person and the difficulty. If an accepted outcome from `plugin-product` exists, cite that file. Do not write the outcome.
2. Sprint questions: at least one question the Friday test could answer. A question is not a feature.
3. Target: who, and which moment. Who uses a person the user named, or the "who it is for" of an accepted brief. Do not invent a name, an age, or a biography.
4. Map: cite an accepted journey map by file name when one exists. If the message describes the situation, cite that sentence. If neither exists, name `/uiux-journey-map` and do not invent the phases.
5. Do not draw a screen and do not record an idea.

## Template

```markdown
# <NNN> — <title>

- State: proposed | accepted
- Source: Knapp, Zeratsky, and Kowitz, Sprint (2016), Monday

## Long-term goal

## Sprint questions

1. <question>

## Target

- Who:
- Moment:

## Map

## Next

`/uiux-solution-sketch` writes one competing idea. This file does not draw it.
```

## Example

State: `accepted`. Long-term goal: in two years, someone booking from a phone knows the table is held. Sprint question: can they tell the table is held on the first try? Target: the person booking from a phone, at the moment they look for the confirmation. Map: cites the journey map when that file exists. Next: `/uiux-solution-sketch`.

## Prerequisites

- **Long-term goal.** In this turn, or cited from an accepted product outcome. If it is missing, template `two-year-outcome`: "In two years, the person who does <task> no longer hits this difficulty: <problem>." Use the task and the problem from an accepted brief or from this turn. If either is unknown, use "the task" and "they cannot yet complete it on a clear path." State: `proposed`. Change it with `/uiux-sprint-frame`. Regenerate with `/uiux-sprint-frame`.
- **Sprint question.** At least one, in this turn. If it is missing, template `one-question`: "Can the person finish <task> on the first attempt, without asking for help?" Use the task from an accepted task analysis, from the brief, or from this turn. If the task is unknown, use "the task." State: `proposed`. Change it with `/uiux-sprint-frame`. Regenerate with `/uiux-sprint-frame`.
- **Target.** Who and which moment, in this turn or in an accepted brief. If the moment is missing, template `target-result`: the moment they see the result of the task. If who is missing, use "the person who does <task>" and do not invent a name. State: `proposed`. Change it with `/uiux-sprint-frame`. Regenerate with `/uiux-sprint-frame`.

The delivery is `accepted` only when the goal, at least one question, and the target all came from the user or from an accepted file, and no template was applied. Any template leaves the delivery `proposed`.

## Prompts

In one message:

```text
/uiux-sprint-frame for reserving a table.
Long-term goal: in two years, someone booking from a phone knows the table is held.
Sprint question: can they tell the table is held on the first try?
Target: the person booking from a phone, at the moment they look for the confirmation.
```

There is no earlier command inside this skill. The brief, the tasks, and the journey map are earlier in the week. Their prompts are in [The week](../SKILL.md#the-week).

## Done

- The long-term goal, at least one sprint question, and a target with who and a moment are present, from the user, from an accepted file, or from the named template.
- Who has no invented name, age, or biography.
- The file cites a journey map or names `/uiux-journey-map`. It does not invent the phases. It does not write a solution, a screen, a prototype, or a test.
- Any template leaves the state `proposed`. The reply names `/uiux-solution-sketch` and does not write that file.
