---
name: evaluate-ui
description: Evaluates an interface without users through heuristics, a cognitive walkthrough, consistency with the UI kit, a flow review, or an implementation review. Use it when reviewing a design or a screen that is already built.
---

# Evaluate the interface

Find problems without calling users in. Each finding says where it is, which rule it breaks, how severe it is, and how to fix it. Measuring with people is `test-with-users`.

Source: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, and Severity Ratings for Usability Problems (0–4). Cognitive walkthrough: Wharton, Rieman, Lewis, and Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide. Consistency is judged against the UI kit. The flow review has no other standard: extra steps, dead ends, and missing states. The implementation review has no standard of its own: the criterion is the handoff and the UI kit. The WCAG audit is done by `adrenaline-accessibility`. This skill asks for it; it does not run it.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Evaluate a screen or a flow that already exists (an `accepted` file, or what the user shows in this turn). If there is nothing to review, follow "When a prerequisite is missing".
4. Do not verify the use case: that is not this evaluation. Do not mark a WCAG criterion as met.
5. When closing heuristics, the walkthrough, the flow, or the implementation review, ask `adrenaline-accessibility` for the review.
6. Do not write HTML or interface code. Do not fix the built screen: write the correction down.

| Request | Piece | Reference |
| --- | --- | --- |
| The 10 heuristics | heuristics | `references/heuristics.md` |
| The four questions per step | cognitive walkthrough | `references/cognitive-walkthrough.md` |
| Drift from the kit | consistency | `references/consistency.md` |
| Steps, dead ends, and states | flow review | `references/flow-review.md` |
| What was built against the handoff | implementation review | `references/implementation-review.md` |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review`, `implementation-review`). Heuristic names stay the Nielsen Norman Group names; a gloss may follow in the artifact language. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it.

`<NNN>-<type>-<topic>.md`. `<type>` is `heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review`, or `implementation-review`. `<NNN>` is the next free integer, three digits, and it is not reused.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

The implementation review stays `proposed` if the handoff is missing or the screen could not be seen. The rest stays `accepted`, unless the user asked for a draft. When you close, say the folder, the file, the `N`, and the state.

## Example

Input: "Review the heuristics of payment when the network fails. The button still says Pay and there is no message."

Output: a Markdown file with one finding. Screen: payment. State: network error. Heuristic: visibility of system status. Severity: 3 (major). Correction: an error message and a retry action; keep the card data. At the end, ask `adrenaline-accessibility` for the review.
