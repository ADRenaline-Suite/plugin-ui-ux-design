---
name: understand-user
description: Analyzes the user's tasks, builds the journey map, and closes the design brief before any screen is drawn. Use it when discovering or defining an interface problem, or when someone asks for tasks, a journey map, or a brief.
---

# Understand the user

Close the problem before drawing. This skill produces the task analysis, the journey map, or the brief. Screens come from `specify-screen`. The order of screens comes from `arrange-screens`.

Source: ISO 9241-210:2019 (understand the context of use and specify requirements). The brief is the output of Define in the Design Council Framework for Innovation (double diamond: discover, define, develop, deliver; it is not linear). Tasks: Nielsen Norman Group, Task Analysis. Journey map: Nielsen Norman Group, Journey Mapping 101.

## Before writing

1. If this turn comes from a command, the piece is already fixed. Otherwise pick one piece from the table. If they ask for two, make both deliveries, each with its own `<NNN>`.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. The use case, if one exists, comes from `adrenaline-project-manager`. If it does not, start from the goal the user states in this turn. If there is no goal, follow "When a prerequisite is missing".
4. The persona comes from the user. Do not invent one. If it is missing and the piece is the journey map, follow "When a prerequisite is missing".
5. Do not draw screens, flows, or tokens in this skill.

| Request | Piece | Reference |
| --- | --- | --- |
| Goal, tasks, subtasks, and order | tasks | `references/tasks.md` |
| One person's path through a scenario | journey map | `references/journey-map.md` |
| Problem, who it is for, constraints, and measurable success | brief | `references/brief.md` |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it. Do not choose another plugin's folder.

Each new file is named `<NNN>-<type>-<topic>.<ext>`. `<NNN>` is the next free integer in that folder, three digits, and it is not reused. `<type>` is `tasks`, `journey-map`, or `brief`. `<topic>` is kebab-case. This skill writes Markdown.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

A new delivery is `accepted`. It is `proposed` only when the user asks for a draft. When you close, say the folder, the file, the `N`, and the state.

## Example

Input: "The goal is to pay an order with a card. The use case is pay the cart."

Output: `ui-ux-design/001-tasks-pay-order.md`, an `accepted` row in `STATUS.md`. The Markdown lists the goal, the tasks in order (review the amount, enter the card, confirm), and the subtasks the user described. It adds neither a persona nor a screen. A request written in Spanish produces the same fields with Spanish prose.
