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

1. The task and its steps come from the task analysis or the `accepted` user flow. If they are not there, ask for them.
2. Walk the story of a new person. Do not assume an unlabeled icon is known.
3. Success on question 4 is that the screen shows the progress. A button that does not change on error fails question 4.
4. Ask `adrenaline-accessibility` for the review. Do not audit WCAG.

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

Accessibility: ask `adrenaline-accessibility` for the review.
```

## Example

Step "confirm the payment" in the network-error state. Question 4: no. The button still says "Pay" and the result does not appear. Correction: show the failure and a retry action, with the card data still filled in.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. Stops the delivery. Earlier command: `/uiux-tasks`.
- **Steps.** An `accepted` user flow, or the steps in this turn. Stops the delivery. Earlier command: `/uiux-user-flow`.

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
