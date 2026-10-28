[🏠 UI/UX Design](../../../README.md) / [Evaluate the interface](../SKILL.md)

# Cognitive walkthrough

Source: Wharton, Rieman, Lewis, and Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide.

## What it fixes

Whether a person who knows the task and does not know this interface can take each step by exploring. It does not measure how fast an expert already is.

## The four questions

At each step, in this order:

1. Will the user try to achieve the right effect?
2. Will the user notice that the correct action is available?
3. Will the user associate the correct action with the effect they are trying to achieve?
4. If the correct action is performed, will the user see that progress is being made?

A "no" is a problem. Note the question, the evidence on the screen, and the correction. Write the questions in the language of the artifact; keep this order.

## How to do it

1. The task and its steps come from the task analysis or the `accepted` user flow. If they are not there, write them with templates `single-task` and `linear-three` and leave this review `proposed`.
2. Walk the story of a new person. Do not assume an unlabeled icon is known.
3. Success on question 4 is that the screen shows the progress. A button that does not change on error fails question 4.
4. Ask `plugin-accessibility` for the review. Do not audit WCAG.

## Template

```markdown
# Cognitive walkthrough — <task>

- Assumed person: knows the task and not this interface
- Origin of the steps: <file>
- Source: Wharton, Rieman, Lewis, and Polson (1994)

## Step <n> — <action>

| Question | Yes? | Evidence |
| --- | --- | --- |
| Will they try the right effect? | | |
| Will they see the action? | | |
| Will they associate the action with the effect? | | |
| Will they see the progress? | | |

- Problem:
- Correction:

Accessibility: ask `plugin-accessibility` for the review.
```

## Example

Step "confirm the payment" in the network-error state. Question 4: no. The button still says "Pay" and the result does not appear. Correction: show the failure and a retry action, with the card data still filled in.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. If neither exists, write it with template `single-task`. Change it with `/uiux-tasks`. Regenerate this walkthrough with `/uiux-cognitive-walkthrough`.
- **Steps.** An `accepted` user flow, or the steps in this turn. If neither exists, write the flow with template `linear-three`. Change it with `/uiux-user-flow`. Regenerate this walkthrough with `/uiux-cognitive-walkthrough`. State of this review: `accepted` when the task and the steps already existed; `proposed` when either was written in this turn from a template.

## Prompts

In one message:

```text
/uiux-cognitive-walkthrough of payment.
The task is pay with a card.
Steps: see the amount, enter the card, confirm. On a network error the button still says Pay.
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

## Done

- Every step of the task has the four questions, in order, each with yes or no and evidence from the screen. A "no" has a problem and a correction. When the task or the steps were written in this turn from a template, the delivery is `proposed` and Assumed says so.
- The assumed person knows the task and not this interface. An unlabeled control is not treated as known.
- No WCAG criterion is assigned. The close asks `plugin-accessibility` for the review.
