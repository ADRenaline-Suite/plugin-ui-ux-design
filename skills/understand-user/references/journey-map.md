[🏠 UI/UX Design](../../../README.md) / [Understand the user](../SKILL.md)

# Journey map

Source: Nielsen Norman Group, Journey Mapping 101.

## What it fixes

The persona the user provided, the scenario, and the phases with actions, thoughts, emotions, and opportunities.

## What it leaves open

The interface solution. An opportunity is not a screen.

## How to do it

1. Copy the persona as the user gave it: name or role, and what is already known about them. If there is no persona, apply template `role-from-task`. Do not invent a name, an age, or a biography.
2. The scenario is the concrete situation in which the goal happens (where, how hurried, with what information). If the user did not give it, apply template `complete-the-task`.
3. The phases follow the order of the tasks, if the tasks already exist. If they do not, take the phases from the user's account. If there is no account either, the phases are the three subtasks of template `single-task` (enter the data, confirm, see the result). Do not invent extra stretches. Thought and emotion without evidence stay "no evidence".
4. In each phase write action, thought, emotion, and opportunity. Thought and emotion come from what the user told (a quote, a complaint, an observation). If there is no evidence, leave the field as "no evidence" and ask. Do not fill in an emotional curve.
5. The opportunity says what would have to change for that phase. Do not draw the screen.

## Template

```markdown
# Journey map — <topic>

- Persona: <as the user gave it>
- Scenario:
- Goal:
- Source: Nielsen Norman Group, Journey Mapping 101.

## Phases

### <phase>
- Action:
- Thought:
- Emotion:
- Opportunity:
```

## Example

Persona (from the user): "Ana pays the shop order once a week from her phone, on the way to work."

Phase "Confirm the payment". Action: accepts the charge. Thought: "no evidence". Emotion: "no evidence". Opportunity: know at once whether the charge went through. That opportunity is written down; the screen is asked of `specify-screen`.

## Prerequisites

- **Persona.** Provided by whoever asks for the map. If it is missing, template `role-from-task`: "Role: the person who does <task>. No name, no age, no biography." Thought and emotion stay "no evidence". State: `proposed`. Change it with `/uiux-journey-map`. Regenerate with `/uiux-journey-map`.
- **Scenario.** The situation in which the path happens, in this turn. If it is missing, template `complete-the-task`: "They want to finish <task>. If it fails, they come back." State: `proposed`. Change it with `/uiux-journey-map`. Regenerate with `/uiux-journey-map`.

## Prompts

In one message:

```text
/uiux-journey-map for confirming the payment.
Persona: Ana pays the order once a week from her phone, on the way to work.
Scenario: she is on the commute and wants to know whether the charge went through.
```

There is no earlier command. The single prompt is the way.

## Done

- The persona is copied as the user gave it, or it is template `role-from-task` with no name, age, or biography. Assumed says which.
- The scenario is the situation the user described, or template `complete-the-task`. Phases follow the tasks if they exist. No stretch was invented. When either template was used, the delivery is `proposed`.
- Each phase has action, thought, emotion, and opportunity. Thought or emotion without evidence says "no evidence".
- An opportunity is not a screen. No interface is drawn.
