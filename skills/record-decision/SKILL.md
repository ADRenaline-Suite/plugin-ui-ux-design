---
name: record-decision
description: Records a design decision with its context, the options, the decision, and the consequences. Use it when the reason the interface ended one way rather than another has to be written down.
---

# Record a decision

Leave a record of a design decision. It does not design the screen: it points at the artifacts that already exist.

Source: Michael Nygard, Documenting Architecture Decisions (2011). The states use the same names: `proposed`, `accepted`, `deprecated`, `superseded`. An `accepted` decision is the one to follow. A newer one does not displace it by being newer.

## Before writing

1. Read `references/decision.md`.
2. The decision has to have been made by the user, or the user asks to leave an option as a proposal. Do not pick the winning option yourself and mark it `accepted`.
3. If the option changes tokens, copy, or the flow, do not rewrite them in this file. Those changes are deliveries of `define-appearance`, `adrenaline-ux-writing`, or `arrange-screens`.
4. Do not write HTML or interface code.

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays `decision`. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it.

The file is `<NNN>-decision-<topic>.md`. `<NNN>` is the next free integer, three digits, and it is not reused.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The row's state is the decision's state.

If the topic already has a file:

- The user asks to amend that same decision: edit the same file, keep the `<NNN>`, and keep `accepted` if it already was.
- The user changes the option: next `<NNN>`, the previous row becomes `superseded` (`sustituye` points at the new `N`), and the new row takes the state that fits.
- New topic: next `<NNN>`.

`proposed` if it is not chosen yet. `accepted` when the user treats it as decided. `deprecated` if it stays readable and is no longer preferred, with no decision that replaces it. `superseded` when another decision replaces it. When you close, say the folder, the file, the `N`, and the state.

## Example

Input: "We keep retry on the same payment screen, not on a new screen. Write it down."

`accepted` output: `021-decision-retry-on-payment.md`. Context: the network error cleared the card. Options: a new screen, or the notice on the same one. Decision: the notice on the same screen, and the data is kept. Consequences: the payment handoff has to show that state.
