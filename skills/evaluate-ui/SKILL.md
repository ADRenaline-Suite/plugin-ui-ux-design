---
name: evaluate-ui
description: Evaluates an interface without users through heuristics, a cognitive walkthrough, consistency with the UI kit, a flow review, or an implementation review. Use it when reviewing a design or a screen that is already built.
---

<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="SKILL.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../README.md)

# Evaluate the interface

Find problems without calling users in. Each finding says where it is, which rule it breaks, how severe it is, and how to fix it. Measuring with people is `test-with-users`.

Source: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, and Severity Ratings for Usability Problems (0–4). Cognitive walkthrough: Wharton, Rieman, Lewis, and Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide. Consistency is judged against the UI kit. The flow review has no other standard: extra steps, dead ends, and missing states. The implementation review has no standard of its own: the criterion is the handoff and the UI kit. The WCAG audit is done by `plugin-accessibility`. This skill asks for it; it does not run it.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Evaluate a screen or a flow that already exists (an `accepted` file, or what the user shows in this turn). If heuristics, the walkthrough, or the flow review have nothing to review, write that screen or path with the template in the reference and leave the review `proposed`. Consistency and the implementation review still stop when the reference says so.
4. Do not verify the use case: that is not this evaluation. Do not mark a WCAG criterion as met.
5. When closing heuristics, the walkthrough, the flow, or the implementation review, ask `plugin-accessibility` for the review.
6. Do not write HTML or interface code. Do not fix the built screen: write the correction down.

| Request | Piece | Reference |
| --- | --- | --- |
| The 10 heuristics | heuristics | [references/heuristics.md](references/heuristics.md) |
| The four questions per step | cognitive walkthrough | [references/cognitive-walkthrough.md](references/cognitive-walkthrough.md) |
| Drift from the kit | consistency | [references/consistency.md](references/consistency.md) |
| Steps, dead ends, and states | flow review | [references/flow-review.md](references/flow-review.md) |
| What was built against the handoff | implementation review | [references/implementation-review.md](references/implementation-review.md) |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review`, `implementation-review`). Heuristic names stay the Nielsen Norman Group names; a gloss may follow in the artifact language. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the Assumed block when a template was applied and the three parts when a prerequisite still stops the delivery. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

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

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["plugin-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it.

`<NNN>-<type>-<topic>.md`. `<type>` is `heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review`, or `implementation-review`. `<NNN>` is the next free integer, three digits, and it is not reused.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

The implementation review stays `proposed` if the handoff is missing or the screen could not be seen. Heuristics, the walkthrough, and the flow review stay `proposed` when the screen or the path was written in this turn from a template. Consistency is not written without a product kit or without a screen to compare. The rest stays `accepted`, unless the user asked for a draft. When you close, say the folder, the file, the `N`, and the state.

## Done

Before you close, evaluate this list and the `## Done` list in the reference for this situation. A command fixes the situation: use the reference that command names. Every item is true, or you fix the delivery in this turn. Do not leave a file that fails an item. Do not mark it `accepted` while an item fails. A template the reference names is applied and recorded under Assumed; the delivery uses the state that reference names. A prerequisite that still stops the delivery is not a failed list: follow "When a prerequisite is missing" and write no files for that piece.

- The situation of this turn is the only one written, unless the request asked for two. Each delivery has its own `<NNN>`.
- Files are only in the output folder, named as Delivery says. `<NNN>` is not reused. `STATUS.md` matches the files and the state this situation allows. A gap the reference leaves as `proposed` stays `proposed`.
- The artifact language matches the request. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Every field the template requires is filled. No placeholder remains (`#…`, `<task>`, `TBD`, lorem ipsum). A field the reference tells you to leave blank until data arrives is blank on purpose, and the state is the one the reference names.
- Nothing this skill forbids was added. The reference names what stays out.
- The reply names the folder, the files, the `N`, and the state. If a template was applied, the reply ends with the Assumed block, one line per template, naming the command that changes it and the command that regenerates this piece. A blank left on purpose names the command that fills it.

## Example

Input: "Review the heuristics of payment when the network fails. The button still says Pay and there is no message."

Output: a Markdown file with one finding. Screen: payment. State: network error. Heuristic: visibility of system status. Severity: 3 (major). Correction: an error message and a retry action; keep the card data. At the end, ask `plugin-accessibility` for the review.
