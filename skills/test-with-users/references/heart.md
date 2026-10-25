# HEART

Source: Rodden, Hutchinson, and Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). The process is goals, signals, and metrics. It complements research with users. It does not replace it. It is not a usability test.

## What it fixes

For a product already launched, which experience goal is pursued, which signal would show it, and which metric would count it.

## Dimensions

Only the ones the user wants to work on. The names are the article's:

| Dimension | Question |
| --- | --- |
| Happiness | What attitude the person using it has |
| Engagement | How much they get involved |
| Adoption | How many new people start using it |
| Retention | How many come back |
| Task success | Whether they complete the task |

## How to do it

1. If the product is not launched, do not invent usage figures. Leave the delivery `proposed` and say that HEART waits for launch. Offer the usability-test plan if what they want is to measure the task now.
2. Each row has a goal (what for), a signal (which behavior or attitude gives it away), and a metric (how it would be counted). The user supplies the threshold. If there is no threshold, the row stays without a number and you ask.
3. Do not design the event, the code, or the dashboard. Instrumentation belongs to the frontend area. Do not use Core Web Vitals as if they were HEART.
4. HEART task success does not replace a test's success rate: one is the product in use, the other is a session.

## Template

```markdown
# HEART — <product>

- Launched: yes | no (this delivery stays proposed)
- Source: Rodden, Hutchinson, and Fu (2010). It does not replace the usability test.
- Instrumentation: outside this plugin.

| Dimension | Goal | Signal | Metric | Threshold |
| --- | --- | --- | --- | --- |
```

## Example

Product launched. Task success. Goal: the person paying knows whether the charge went through. Signal: they do not retry the same order. Metric: share of orders with a single charge attempt. The user writes the threshold. This file does not define the analytics event.

## Prerequisites

- **Product launched.** If it is not launched yet, the delivery stays `proposed`. Does not stop the delivery: the delivery stays `proposed`. Earlier command: `/uiux-usability-test`.

## Prompts

In one message:

```text
/uiux-heart of payment.
The product is already launched.
Task success. Goal: the person paying knows whether the charge went through.
Signal: they do not retry the same order.
Metric: share of orders with a single charge attempt. Threshold: <you supply it>.
```

In order, omitting the ones already met:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```
