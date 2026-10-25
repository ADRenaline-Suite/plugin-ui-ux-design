# Test analysis

Source: ISO 9241-11:2018. Effectiveness is the success rate. Efficiency is time, errors, and assistance. Satisfaction, in this plugin, is Brooke's SUS (1996) when the session used it. Problems are ordered with the Nielsen Norman Group severity (0–4), the same scale as `evaluate-ui`.

## What it fixes

Success rate per task, time, problems ordered by severity, and, if there was a SUS, the score.

## How to do it

1. Start from the rows the user hands over. Do not estimate a time that was not written down. If there is no data, leave the delivery `proposed`.
2. Write the observation CSV: `participant,task,success,time_s,errors,assistance,notes`. `success` is `yes`, `no`, or `partial`. One row per participant and task. Prose in `notes` follows the language of the artifact.
3. Effectiveness: successes / attempts, per task. Count `partial` apart; do not add it as success.
4. Efficiency: the median time of those with `success` = `yes`, and the number of errors and of assists. If there are fewer than two times, do not compute a median: list the values.
5. Each observed problem names the task, the severity (0 is not a problem, 1 cosmetic, 2 minor, 3 major, 4 catastrophe), and the design correction. It is not a WCAG finding.
6. SUS, only if Brooke's questionnaire was used, or a published translation of those ten items. If they used another questionnaire, do not call it SUS: report it under its own name.

### SUS score

Brooke's items (1996), in his English. The answer is 1–5.

1. I think that I would like to use this system frequently.
2. I found the system unnecessarily complex.
3. I thought the system was easy to use.
4. I think that I would need the support of a technical person to be able to use this system.
5. I found the various functions in this system were well integrated.
6. I thought there was too much inconsistency in this system.
7. I would imagine that most people would learn to use this system very quickly.
8. I found the system very cumbersome to use.
9. I felt very confident using the system.
10. I needed to learn a lot of things before I could get going with this system.

Contribution of items 1, 3, 5, 7, and 9: answer − 1. Contribution of items 2, 4, 6, 8, and 10: 5 − answer. SUS = sum of the ten contributions × 2.5. The result runs from 0 to 100. Brooke does not define a "pass" cutoff. Do not add a letter or an adjective. Deliver each participant's score and the mean.

SUS CSV, the same `<NNN>` if it belongs to this delivery, or this delivery's `<NNN>` if the plan was another delivery: `participant,item,answer`. If the plan and the analysis are different deliveries, the analysis CSV carries the analysis `<NNN>`.

7. Close in the terms of ISO 9241-11: effectiveness, efficiency, and satisfaction, for these users, this task, and this context. Do not generalize to "the interface is usable".

## Template

```markdown
# Test analysis — <task>

- Plan:
- Context of use:
- Data: <CSV file>
- Source: ISO 9241-11:2018. SUS: Brooke (1996), if it was used.

## Per task

| Task | Attempts | Successes | Partials | Success | Time (median, s) |
| --- | --- | --- | --- | --- | --- |

## Problems

| Severity | Task | Problem | Correction |
| --- | --- | --- | --- |

## SUS

| Participant | Score |
| --- | --- |
| Mean | |

## ISO 9241-11 reading

- Effectiveness:
- Efficiency:
- Satisfaction:
```

## Example

Four of five complete "pay with a card" (success 0.8). One person sees the "Pay" button unchanged when the network fails: severity 3. SUS of one participant with answers 4,2,5,1,4,2,5,1,4,2: contributions 3+3+4+4+3+3+4+4+3+3 = 34; 34 × 2.5 = 85. Report 85, with no letter.

## Prerequisites

- **Data.** The test rows, in this turn. Without rows, the delivery stays `proposed`. Does not stop the delivery: the delivery stays `proposed`. Earlier command: `/uiux-usability-test`.

## Prompts

In one message:

```text
/uiux-test-analysis of pay with a card.
Data: participant, task, success, time, problem.
Paste the rows here. SUS, if there was one: the ten answers.
```

In order, omitting the ones already met:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```
