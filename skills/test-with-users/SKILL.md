---
name: test-with-users
description: Plans and analyzes a usability test, a card sort, a tree test, or HEART metrics. Use it when someone asks to measure with users or to define metrics for a product that is already launched. It does not recruit or run sessions.
---

# Test with users

Plan the session and analyze the data a person has collected. Recruiting participants and running the session is done by a person, not by this skill.

Source: ISO 9241-11:2018 (effectiveness, efficiency, and satisfaction of specified users, with specified goals, in a context of use). Test: Nielsen Norman Group, Usability Testing 101. SUS: Brooke (1996). Card sorting and tree testing: Nielsen Norman Group. HEART: Rodden, Hutchinson, and Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). HEART does not replace the usability test.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Do not invent participants, quotes, or times. If the analysis has no data, write the plan and leave the results blank, or stop and ask for them.
4. The usability test does not verify the use case. The test scenario from `adrenaline-qa-engineer` is a different artifact.
5. Do not instrument metrics or measure Core Web Vitals. That belongs to the frontend area.
6. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Session plan | usability test | `references/usability-test.md` |
| Success, time, problems, and SUS | test analysis | `references/test-analysis.md` |
| How people group the content | card sorting | `references/card-sorting.md` |
| Whether people find an item in the sitemap | tree testing | `references/tree-testing.md` |
| Goals, signals, and metrics of a launched product | HEART | `references/heart.md` |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`usability-test`, `test-analysis`, `card-sorting`, `tree-testing`, `heart`). CSV column names stay the English names in the reference; prose in the cells follows the artifact. SUS items stay in Brooke's English. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it.

`<NNN>` is the next free integer, three digits, and it is not reused. `<type>` is `usability-test`, `test-analysis`, `card-sorting`, `tree-testing`, or `heart`. The plan is Markdown. Observations, SUS, card sorting, and tree testing add a CSV with the same `<NNN>`: `<NNN>-<type>-<topic>.csv`.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

An analysis without data stays `proposed`. A complete plan is `accepted`. HEART for a product that is not launched yet stays `proposed`, and the delivery says it does not apply yet. When you close, say the folder, the files, the `N`, and the state.

## Example

Input: "Test plan for the task pay with a card. Five people who have already bought in the shop take part. Do not recruit."

Output: `018-usability-test-pay.md` with the scenario task "You reach the end of the order and want it paid with the card you already use", without saying which button to press, and the criterion of what to write down. It does not include participant names.
