---
name: arrange-screens
description: Arranges the screens of a task into a user flow, a wireflow, or a sitemap. Use it when someone asks for the path between screens, that same path with wireframes, or the map of how screens are grouped.
---

# Arrange screens

Produce the user flow, the wireflow, or the sitemap. These are UX artifacts. They are not UML diagrams. An activity diagram or a state machine is asked of `adrenaline-uml-diagrams`.

Source: the task the flow completes follows Nielsen Norman Group, Task Analysis (goal, tasks, subtasks, order). The user flow, the wireflow, and the sitemap have no other standard in this plugin's sources: they show that order as a path or as a map.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Each screen in the flow names the task or the use case it covers. If the task is not stated, follow "When a prerequisite is missing".
4. Do not draw the final visual appearance. The wireflow uses gray wireframes, not mocks.
5. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Path to complete a task | user flow | `references/user-flow.md` |
| That path with a wireframe at each step | wireflow | `references/wireflow.md` |
| Map of screens and groups | sitemap | `references/sitemap.md` |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`user-flow`, `wireflow`, `sitemap`). `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it. Do not choose another plugin's folder.

Each new file is named `<NNN>-<type>-<topic>.<ext>`. `<NNN>` is the next free integer in that folder, three digits, and it is not reused. `<type>` is `user-flow`, `wireflow`, or `sitemap`. The user flow and the sitemap are Markdown with Mermaid. The wireflow adds one SVG per screen: `<NNN>-wireflow-<topic>-<screen>.svg`, same `<NNN>`.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

A new delivery is `accepted`. It is `proposed` only when the user asks for a draft or a step has no destination. When you close, say the folder, the files, the `N`, and the state.

## Example

Input: "User flow for pay with a card: the charge can succeed or fail."

Output: `ui-ux-design/004-user-flow-pay.md` with a Mermaid diagram of three screens (details, result, error) and the return from error to details. It is not an activity diagram.
