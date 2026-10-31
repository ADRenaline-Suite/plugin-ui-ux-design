---
name: specify-screen
description: Produces the sketch, wireframe, mock, prototype, or handoff of a screen, from least to most concrete. Use it when someone asks to draw or specify a screen so it can be built.
---

<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="SKILL.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../README.md)

# Specify a screen

Produce one screen. The handoff is the piece from which the screen can be built without guessing. This skill closes that delivery.

Source: ISO 9241-210:2019 (produce solutions). States: Scott Hurff, The UI Stack, plus success and, when they apply, no permission and offline. Fallback breakpoints: Material Design 3 (compact &lt;600 dp, medium 600–839, expanded 840–1199, large 1200–1599, extra-large ≥1600), by window width. Native platform: Apple Human Interface Guidelines, Material Design 3, or Fluent 2. Text expansion: W3C Internationalization, Text size in translation. Copy is written by `plugin-ux-writing`. Accessibility notes are specified by `plugin-accessibility`.

## Before drawing

1. If this turn comes from a command, the piece is already fixed. Otherwise pick one from the table.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill. Exception: if there is no `accepted` kit, write the kit with `define-appearance` before the mock or the handoff. That skill reads `references/presets.md`. A named preset or the tokens in this turn choose the kit. If neither arrives, the kit is preset `plain`.
3. Each screen names the user task or the use case it covers. If the task is not stated, write it in this turn with template `single-task` and record it under Assumed.
4. The order is sketch, wireframe, mock, prototype, handoff. Sketch and wireframe stay optional. Write an earlier piece in this turn only when the reference of the piece they asked for says that piece is required and it is missing.
5. The mock needs a path: an `accepted` user flow, the path in this turn, or template `linear-three` written as a user flow in this turn. If there is no `accepted` UI kit, write one with `define-appearance` before the mock: the named preset, the tokens in this turn, or `plain` when none is selected. Do not invent a palette. Record each template under Assumed.
6. Platform and breakpoints: the product's, if they exist. If there are no breakpoints, use Material Design 3. If the product is native, follow that platform's guide. If that guide contradicts the UI kit, say so and follow the kit.
7. Real content, what the user already gave or what `plugin-ux-writing` gave. No lorem ipsum. In the wireframe, the mock, and the handoff, try a long string and the expansion on translation (a string of up to 10 characters can grow to 200–300%). If the product uses right-to-left writing, include an RTL frame. Do not translate the product: translation itself is out of scope.
8. Themes: if the product has light mode, dark mode, or brand variants, the mock and the handoff cover them.
9. States of every screen: ideal, empty, loading, partial, error, and success. When they apply, also no permission and offline. On error, what the person typed is kept. If a state does not apply, the Markdown says why.
10. An activity diagram or a state machine for the screen is asked of `plugin-uml-diagrams`. Do not draw it here.
11. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Idea and blocks | sketch | [references/sketch.md](references/sketch.md) |
| Hierarchy and layout | wireframe | [references/wireframe.md](references/wireframe.md) |
| Visual appearance | mock | [references/mock.md](references/mock.md) |
| Path across screens | prototype | [references/prototype.md](references/prototype.md) |
| Specification for building | handoff | [references/handoff.md](references/handoff.md) |

| Piece | What it fixes | What it leaves open |
| --- | --- | --- |
| Sketch | Idea and blocks | Measure, color, final copy |
| Wireframe | Hierarchy and layout per breakpoint | Visual style |
| Mock | Visual appearance of one screen, per theme | Interaction across screens |
| Prototype | Path that opens in the browser | Build specification |
| Handoff | Measures, states, copy, behavior, accessibility notes | — |

## SVG

One per screen. SVG 1.1, with `xmlns="http://www.w3.org/2000/svg"`, a `viewBox`, and a background rectangle. Text in `<text>`, `font-family="system-ui, Segoe UI, sans-serif"`. No external images, no scripts, and no `foreignObject`.

Inside that file, one frame per state that changes what is visible. A breakpoint is drawn again only when the layout changes (columns, what is shown, what stacks). If it only grows, the Markdown says so and the frame is not repeated. Themes are frames of the ideal state when color or type changes. Each frame has a label (`Ideal · Compact`, `Error · Dark`). Those labels follow the language of the artifact.

The Markdown is `<NNN>-<type>-<topic>.md`. Each SVG is `<NNN>-<type>-<topic>-<screen>.svg`. Same delivery, same `<NNN>`.

## Language

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`sketch`, `wireframe`, `mock`, `prototype`, `handoff`). `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the Assumed block when a template was applied and the three parts when a prerequisite still stops the delivery. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

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

`<NNN>` is the next free integer in that folder, three digits, and it is not reused. `<type>` is `sketch`, `wireframe`, `mock`, `prototype`, or `handoff`. `<topic>` and `<screen>` are kebab-case.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

Keep `<folder>/ORIGIN.json` beside `STATUS.md`. It is not an `<NNN>` file and it has no row in `STATUS.md`. Write it when the folder is created. On a later delivery, write it again only when it is missing or a field differs. The fields are `suite` `ADRenaline-Suite`, `plugin` `plugin-ui-ux-design`, `repository` `https://github.com/ADRenaline-Suite/plugin-ui-ux-design`, and `convention` `adr-001`. The marker names the folder. It does not say that each file inside is unchanged.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

The handoff stays `proposed` when the copy or the accessibility notes are missing, or when the mock was written in this turn from a template. The mock is delivered with preset `plain` when no kit, no tokens, and no named preset arrive. The rest is `accepted`, unless the user asks for a draft. When you close, say the folder, the files, the `N`, and the state.

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

Input: "Sketch of the payment screen. The task is pay with a card. Web platform. There is no UI kit yet."

`accepted` output:

- `ui-ux-design/001-sketch-payment.md`
- `ui-ux-design/001-sketch-payment-payment.svg`
- Row `001` in `STATUS.md` for each file.

The Markdown names the task "pay with a card", lists the six states, and says empty does not apply because the amount already comes from the order. The SVG has two blocks in the ideal state (amount, card) and the error state keeps that data plus a message block. There are no measures and no brand color. A request written in Spanish uses Spanish labels in the SVG and in the Markdown.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 360 640">
  <rect width="360" height="640" fill="#f4f4f4"/>
  <text x="16" y="32" font-family="system-ui, Segoe UI, sans-serif" font-size="14">Ideal · Compact</text>
  <rect x="16" y="48" width="328" height="64" fill="#ffffff" stroke="#222"/>
  <text x="32" y="84" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Order amount</text>
  <rect x="16" y="128" width="328" height="120" fill="#ffffff" stroke="#222"/>
  <text x="32" y="164" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Card</text>
  <rect x="16" y="264" width="328" height="48" fill="#ffffff" stroke="#222"/>
  <text x="32" y="294" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Pay</text>
</svg>
```
