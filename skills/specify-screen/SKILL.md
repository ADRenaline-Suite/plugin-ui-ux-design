---
name: specify-screen
description: Produces the sketch, wireframe, mock, prototype, or handoff of a screen, from least to most concrete. Use it when someone asks to draw or specify a screen so it can be built.
---

# Specify a screen

Produce one screen. The handoff is the piece from which the screen can be built without guessing. This skill closes that delivery.

Source: ISO 9241-210:2019 (produce solutions). States: Scott Hurff, The UI Stack, plus success and, when they apply, no permission and offline. Fallback breakpoints: Material Design 3 (compact &lt;600 dp, medium 600–839, expanded 840–1199, large 1200–1599, extra-large ≥1600), by window width. Native platform: Apple Human Interface Guidelines, Material Design 3, or Fluent 2. Text expansion: W3C Internationalization, Text size in translation. Copy is written by `adrenaline-ux-writing`. Accessibility notes are specified by `adrenaline-accessibility`.

## Before drawing

1. If this turn comes from a command, the piece is already fixed. Otherwise pick one from the table.
2. Read only `references/<piece>.md` for the piece they asked for. Do not read references from another skill. Exception: if this turn brings the UI kit tokens and there is no `accepted` kit, write the kit with `define-appearance` (`references/ui-kit.md` of that skill) and then the piece.
3. Each screen names the user task or the use case it covers. If the task is not stated (neither in an `accepted` task analysis nor in this turn), follow "When a prerequisite is missing". Do not leave sketch without that task.
4. The order is sketch, wireframe, mock, prototype, handoff. If they ask for a piece and the previous one does not exist, it can be done when the task is stated and, for mock or later, the path is already decided. Do not fill in the earlier pieces on your own. Do write them in this turn when the prompt brings their data.
5. Do not move on to mock if the path is not decided: an `accepted` user flow, or the path in this turn. Do not move on to mock if there is no `accepted` UI kit and no tokens in this turn. If the path or the kit is missing, follow "When a prerequisite is missing".
6. Platform and breakpoints: the product's, if they exist. If there are no breakpoints, use Material Design 3. If the product is native, follow that platform's guide. If that guide contradicts the UI kit, say so and follow the kit.
7. Real content, what the user already gave or what `adrenaline-ux-writing` gave. No lorem ipsum. In the wireframe, the mock, and the handoff, try a long string and the expansion on translation (a string of up to 10 characters can grow to 200–300%). If the product uses right-to-left writing, include an RTL frame. Do not translate the product: translation itself is out of scope.
8. Themes: if the product has light mode, dark mode, or brand variants, the mock and the handoff cover them.
9. States of every screen: ideal, empty, loading, partial, error, and success. When they apply, also no permission and offline. On error, what the person typed is kept. If a state does not apply, the Markdown says why.
10. An activity diagram or a state machine for the screen is asked of `adrenaline-uml-diagrams`. Do not draw it here.
11. Do not write HTML or interface code.

| Request | Piece | Reference |
| --- | --- | --- |
| Idea and blocks | sketch | `references/sketch.md` |
| Hierarchy and layout | wireframe | `references/wireframe.md` |
| Visual appearance | mock | `references/mock.md` |
| Path across screens | prototype | `references/prototype.md` |
| Specification for building | handoff | `references/handoff.md` |

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

The instructions stay in English. Write the artifact in the language of the request. If the request names a language, use that one. Otherwise use the language the request is written in. Keep names the person already used. Translate the headings of the reference template and keep the same fields. The type in the file name stays the English piece id (`sketch`, `wireframe`, `mock`, `prototype`, `handoff`). `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. The reply uses that same language, including the three parts when a prerequisite is missing. The prompts in the reference are the English wording: show them in the language of the request and keep the command names.

## When a prerequisite is missing

A prerequisite is met by an `accepted` file of that piece, or by the fact written in this turn. The piece reference names the prerequisites, says whether they stop the delivery, and gives the prompts.

If a stopping prerequisite is missing and this turn does not bring it, do not write files for this piece. Reply with only this, in the language of the request:

1. "Missing:" and the names that are missing.
2. "In one message:" and the single prompt from the reference. Fill it with what the person already said. Where a value is missing, leave the gap (`#…`, `<task>`). Do not invent a palette, a persona, participants, or copy.
3. "Or, in this order:" and the earlier commands that are still missing, in the order of the reference, each with its prompt. Omit this block if there is no earlier command. Omit commands whose prerequisite is already met.

Then stop. If the prerequisite does not stop the delivery, write the artifact as the reference says and, when you close, say in the same shape which command completes it.

## Delivery

The folder is `ui-ux-design/` at the project root. If `.cursor/adrenaline.json` has `outputDirs["adrenaline-ui-ux-design"]` set to a relative path, without `..` and not absolute, use that path. If the file, the key, or a valid path is missing, use `ui-ux-design/` and, in the last case, say so. Create the folder if it does not exist. Do not write outside it. Do not choose another plugin's folder.

`<NNN>` is the next free integer in that folder, three digits, and it is not reused. `<type>` is `sketch`, `wireframe`, `mock`, `prototype`, or `handoff`. `<topic>` and `<screen>` are kebab-case.

Keep `<folder>/STATUS.md` with columns `N`, `archivo`, `estado`, `sustituye`, and `notas`. The states are `proposed`, `accepted`, `deprecated`, and `superseded`. When choosing what to follow, the order is `accepted`, then `proposed`, then `deprecated`, then `superseded`.

If the topic already has a file:

- The user asks to change that delivery: edit the same files, keep the `<NNN>`, and leave it `accepted`.
- The user asks for a replacement or a new decision on the same topic: take the next `<NNN>`, mark the previous row `superseded` (`sustituye` points at the new `N`), and leave the new row `accepted`.
- Otherwise: next `<NNN>` and an `accepted` row.

The handoff stays `proposed` when the copy or the accessibility notes are missing. Without an `accepted` kit and without tokens in this turn, the mock is not delivered. The rest is `accepted`, unless the user asks for a draft. When you close, say the folder, the files, the `N`, and the state.

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
