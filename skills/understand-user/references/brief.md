# Design brief

Source: Design Council, Framework for Innovation (double diamond). The brief is the output of Define. ISO 9241-210:2019: usage requirements are specified before the solution is produced. The diamond is not linear: what is learned while evaluating can send the work back to an earlier phase.

## What it fixes

The problem, who it is for, the constraints, and the measurable success criteria.

## What it leaves open

The form of the interface. The brief does not choose sketch, wireframe, or mock.

## How to do it

1. The problem is one concrete person's difficulty, not a list of screens.
2. "Who it is for" uses the persona the user provided. If there is no persona yet, describe who the user named and do not invent a profile.
3. Constraints: platform (web, iOS, Android, Windows), the UI kit if one exists, and deadlines if there are any. If the platform is not stated, ask for it.
4. Each success criterion can be checked: what is measured, on which task, and against which threshold. If the user has no threshold, ask. Do not put in a percentage of your own.
5. If a later test or review contradicts the brief, do not rewrite it in silence: that is another decision, with the next `<NNN>`, or an amendment if the user asks for one.

## Template

```markdown
# Brief — <topic>

- Problem:
- Who it is for:
- Constraints:
  - Platform:
  - UI kit:
  - Deadlines:
- Source: Design Council, Framework for Innovation. ISO 9241-210:2019.

## Success criteria

| Criterion | Task | How it is measured | Threshold |
| --- | --- | --- | --- |
```

## Example

Problem: the person paying does not know whether the charge went through. Who it is for: the person the user named. Platform: web. UI kit: the shop's, if it exists. Criterion: on the task "confirm the payment", the person identifies the result without asking; the user supplies the threshold.

## Prerequisites

- **Problem.** What fails for the person, in this turn. Stops the delivery. No earlier command.
- **Platform.** Web or the native platform, in this turn. Stops the delivery. No earlier command.
- **Success criterion.** Measurable, with the threshold given by whoever asks for the brief. Stops the delivery. No earlier command.

## Prompts

In one message:

```text
/uiux-brief for payment.
Problem: the person paying does not know whether the charge went through.
Who it is for: the person who pays the order from a phone.
Platform: web.
Success criterion: on the task confirm the payment, they identify the result without asking. You supply the threshold.
```

There is no earlier command. The single prompt is the way.
