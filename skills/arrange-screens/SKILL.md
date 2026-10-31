---
name: arrange-screens
description: Arranges the screens of a task into a user flow, a wireflow, or a sitemap. Use it when someone asks for the path between screens, that same path with wireframes, or the map of how screens are grouped.
---

<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="SKILL.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../README.md)

# Arrange screens

Produce the user flow, the wireflow, or the sitemap. These are UX artifacts. They are not UML diagrams. An activity diagram or a state machine is asked of `plugin-uml-diagrams`.

Source: the task the flow completes follows Nielsen Norman Group, Task Analysis (goal, tasks, subtasks, order). The user flow, the wireflow, and the sitemap have no other standard in this plugin's sources: they show that order as a path or as a map.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Each screen in the flow names the task or the use case it covers. If the task is not stated, write it in this turn with template `single-task` and record it under Assumed.
4. Do not draw the final visual appearance. The wireflow uses gray wireframes, not mocks.
5. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Path to complete a task | user flow | [references/user-flow.md](references/user-flow.md) |
| That path with a wireframe at each step | wireflow | [references/wireflow.md](references/wireflow.md) |
| Map of screens and groups | sitemap | [references/sitemap.md](references/sitemap.md) |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`user-flow`, `wireflow`, `sitemap`). `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the Assumed block when a template was applied and the three parts when a prerequisite still stops the delivery. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names each prerequisite, the template that fills it, the state that template leaves, the command that replaces it, and the command that regenerates this piece.

Use sources in this order: an `accepted` file, then the fact written in this turn, then the template. Do not apply a template when a higher source exists.

When the reference gives a template, write the files. In the same turn, also write the earlier pieces that reference says to write, each with its own `<NNN>`, and only those. Do not write a piece this request does not need.

In the Markdown, add a heading `Assumed`, translated to the language of the request. One line per template: the gap, the template id, and the value used. `STATUS.md` `notas` for that row lists the template ids (`assumed: plain, linear-three`).

After the folder, the files, the `N`, and the state, close with this block, in the language of the request. One line per template. Omit the block when nothing was assumed.

```text
Assumed automatically (there was no accepted file and this message did not bring it):
- <gap>: template <id> (<value used>). Change it with <command>. Regenerate with <command>.
```

A template the reference marks `accepted` leaves the delivery `accepted`. A template the reference marks `proposed` leaves it `proposed`. Each line says the value is a starting point, taken automatically, and is not a fact from the user, from research, or from another plugin.

If the reference gives no template and does not stop, write the artifact as it says and, when you close, name the command that fills the gap. Say that the blank was left on purpose and that nothing was invented for it.

Two checks still stop the delivery. Write no files for that piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`).
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Those two are a screenshot or a URL for `/uiux-implementation-review`, and a product UI kit for `/uiux-consistency` (an `accepted` kit, or tokens in this turn). Consistency also stops when no `accepted` screen exists and this turn does not describe one. Do not draw a screen in order to compare it, and do not compare against preset `plain`.

Do not invent copy, accessibility notes, test rows, HEART figures, a chosen decision, a persona's name or biography, or a palette. Those gaps stay blank, or use the template the reference names, and the delivery stays in the state the reference names.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["plugin-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it. Do not choose another plugin's folder.

Each new file is named `<NNN>-<type>-<topic>.<ext>`. `<NNN>` is the next free integer in that folder, three digits, and it is not reused. `<type>` is `user-flow`, `wireflow`, or `sitemap`. The user flow and the sitemap are Markdown with Mermaid. The wireflow adds one SVG per screen: `<NNN>-wireflow-<topic>-<screen>.svg`, same `<NNN>`.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

Keep `<folder>/ORIGIN.json` beside `STATUS.md`. It is not an `<NNN>` file and it has no row in `STATUS.md`. Write it when the folder is created. On a later delivery, write it again only when it is missing or a field differs. The fields are `suite` `ADRenaline-Suite`, `plugin` `plugin-ui-ux-design`, `repository` `https://github.com/ADRenaline-Suite/plugin-ui-ux-design`, and `convention` `adr-001`. The marker names the folder. It does not say that each file inside is unchanged.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

A new delivery is `accepted`. It is `proposed` only when the user asks for a draft or a step has no destination. When you close, say the folder, the files, the `N`, and the state.

## Done

Before you close, evaluate this list and the `## Done` list in the reference for this situation. A command fixes the situation: use the reference that command names. Every item is true, or you fix the delivery in this turn. Do not leave a file that fails an item. Do not mark it `accepted` while an item fails. A template the reference names is applied and recorded under Assumed; the delivery uses the state that reference names. A prerequisite that still stops the delivery is not a failed list: follow "When a prerequisite is missing" and write no files for that piece.

- The situation of this turn is the only one written, unless the request asked for two. Each delivery has its own `<NNN>`.
- Files are only in the output folder, named as Delivery says. `<NNN>` is not reused. `STATUS.md` matches the files and the state this situation allows. A gap the reference leaves as `proposed` stays `proposed`.
- `ORIGIN.json` is in the output folder. Its four fields match this plugin. It has no row in `STATUS.md`.
- The artifact language matches the request. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Every field the template requires is filled. No placeholder remains (`#…`, `<task>`, `TBD`, lorem ipsum). A field the reference tells you to leave blank until data arrives is blank on purpose, and the state is the one the reference names.
- Nothing this skill forbids was added. The reference names what stays out.
- The reply names the folder, the files, the `N`, and the state. If a template was applied, the reply ends with the Assumed block, one line per template, naming the command that changes it and the command that regenerates this piece. A blank left on purpose names the command that fills it.

## Example

Input: "User flow for pay with a card: the charge can succeed or fail."

Output: `ui-ux-design/004-user-flow-pay.md` with a Mermaid diagram of three screens (details, result, error) and the return from error to details. It is not an activity diagram.
