---
name: define-appearance
description: Sets the visual direction of the interface in a moodboard and the UI kit with its tokens. Use it when someone asks how the interface looks, or asks for the components or the design tokens.
---

# Define the appearance

Produce the moodboard or the UI kit. The kit governs the mock and the handoff. If the product already has a kit, start from that one and do not invent another.

Source of the tokens: Design Tokens Format Module 2025.10 and Color Module 2025.10 (W3C Design Tokens Community Group, Final Community Group Report, 28 October 2025). They are stable and they are not a W3C standard. Do not cite a later draft. Components follow the product's UI kit. Atomic Design (Brad Frost) is only a possible grouping model when the product does not have its own yet. The moodboard has no single standard in the sources: it records references, color, type, and tone applied to screens.

## Before writing

1. If this turn comes from a command, the piece is already fixed.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill.
3. Platform: web, or the native guide (Apple Human Interface Guidelines, Material Design 3, Fluent 2). If the guide contradicts the kit, say so and follow the kit.
4. Themes: only the ones the product has (light, dark, brand variants). Do not add a theme.
5. Do not draw the flow or audit WCAG. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Visual direction | moodboard | `references/moodboard.md` |
| Components, tokens, and rules | UI kit | `references/ui-kit.md` |

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`moodboard`, `ui-kit`). `$description` on a token follows the artifact language. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it. Do not choose another plugin's folder.

`<NNN>` is the next free integer, three digits, and it is not reused. The moodboard is `<NNN>-moodboard-<topic>.md` plus one SVG per sample screen, `<NNN>-moodboard-<topic>-<screen>.svg`. The UI kit is `<NNN>-ui-kit-<topic>.md` and `<NNN>-ui-kit-<topic>.tokens.json`. Same delivery, same `<NNN>`.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

A new delivery is `accepted`. It is `proposed` if the user asks for a draft or the kit does not cover the themes the product already has. When you close, say the folder, the files, the `N`, and the state.

## Example

Input: "Minimal UI kit for the shop, light theme. Action blue #0066cc, white background, near-black text, 16 px space."

Output: `012-ui-kit-shop.md` and `012-ui-kit-shop.tokens.json`, with color, type, space, radius, and elevation in DTCG 2025.10, and the button with its states.
