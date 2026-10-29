<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="usability-test.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Test with users](../SKILL.md)

# Usability test

Source: Nielsen Norman Group, Usability Testing 101. ISO 9241-11:2018 defines what can be concluded afterwards (effectiveness, efficiency, satisfaction); this manual only plans the session.

## What it fixes

Scenario tasks, who takes part, what to observe, and how to record it.

## What it leaves open

The results. `test-analysis` calculates them when the data exists. This plugin does not recruit or moderate.

## How to do it

1. The goal of the test is a task already stated. If it is not, write it with template `single-task`.
2. Each task is a realistic scenario and does not contain the answer. Do not say the button name or the path. "Pay your order with a card" is right. "Press Pay and then Done" is not.
3. Participants: the criteria the user gives (who and how many). If they do not give the number, apply template `nielsen-5`: 5 people, a qualitative session, not recruited. Cite Nielsen, Why You Only Need to Test with 5 Users (2000). Do not invent names. A qualitative session is not a statistical calculation; do not present it as one.
4. What to observe: whether they completed the task, in how much time, what errors, whether they asked for help, and verbatim quotes. The person who moderates writes it down. This plan's CSV may go out empty, with the header, for that session; the analysis loads the data.
5. If the SUS will be given, say so in the plan and reserve the ten items for the end. Do not mix them with the task.
6. The test scenario from `plugin-qa-engineer` is not copied here.

## Template

```markdown
# Usability test — <task>

- Goal of the session:
- Participants: <criteria and number the user gave>
- Who moderates: a person. This plugin does not recruit or run the session.
- Source: Nielsen Norman Group, Usability Testing 101.

## Scenario tasks

1. <scenario that does not reveal the control>

## What to write down

| Datum | How |
| --- | --- |
| Success | yes, no, or partial, per task |
| Time | seconds per task |
| Errors and assistance | what happened |
| Quotes | verbatim |

## Record

CSV `<NNN>-usability-test-<topic>.csv` with columns `participant,task,success,time_s,errors,assistance,notes`. One row per participant and task. It is filled in during the session.
```

## Example

Scenario task: "You finish the order on the way to work and want it paid with the card you already use." It does not say the control is called "Pay". Participants: five people who have already bought, the number given by the user.

## Prerequisites

- **Task.** The task to test, in this turn, or an `accepted` task analysis. If neither exists, write it with template `single-task`. State: `accepted`. Change it with `/uiux-tasks`. Regenerate this plan with `/uiux-usability-test`.
- **Number of participants.** Given by whoever asks for the plan. If it is missing, template `nielsen-5`: 5 people, qualitative, not recruited. Nielsen, Why You Only Need to Test with 5 Users (2000). Do not invent names. State: `accepted`. Change it with `/uiux-usability-test`. Regenerate with `/uiux-usability-test`.

## Prompts

In one message:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```

In order, omitting the ones already met:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

## Done

- The goal is a task already stated, or template `single-task`. Each scenario task does not name the control or the path.
- Participants are the criteria and the number the user gave, or template `nielsen-5` when the number was missing. Assumed says which, and that they are not recruited. No names were invented. The file says a person moderates and this plugin does not recruit or run the session.
- What to write down covers success, time, errors, help, and quotes. The CSV may be header-only. Results are not calculated here. It is not a `plugin-qa-engineer` test scenario.
