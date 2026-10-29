<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="mock.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Specify a screen](../SKILL.md)

# Mock

Source: the product's UI kit. Tokens written in this turn follow the Design Tokens Format Module 2025.10; the token file is produced by `define-appearance`, not by this manual. Breakpoints: the product's, or Material Design 3.

## What it fixes

The visual appearance of one screen, with the UI kit tokens and per theme.

## What it leaves open

The path to other screens and the build specification (annotated measures, behavior, accessibility). That is the prototype and the handoff.

## How to do it

1. The path has to be decided: an `accepted` user flow, or the path in this turn. If neither exists, write the user flow in this turn with template `linear-three`.
2. Use the tokens of the `accepted` UI kit. If there is no kit, write it with `define-appearance` and then the mock. A named preset or the tokens in this turn choose it. If neither arrives, the kit is preset `plain`. Do not invent a palette.
3. One frame per theme in the ideal state (light, dark, brand variant), only the themes the product has. Do not add dark mode if the product does not have it.
4. Real copy, from the user or from `plugin-ux-writing`. If the final copy is missing, use the labels already agreed and say so in the Markdown; do not write new microcopy.
5. Draw the states that change the appearance. Error keeps what was typed and shows what failed.
6. The SVG uses the kit colors in `fill` and `stroke`. Still no redlines: the dimensions belong to the handoff.

## Markdown template

```markdown
# Mock — <screen>

- Task or use case:
- Path decided: <user flow file, or "described in this turn">
- UI kit: <accepted file> | preset <id> | tokens from this turn
- Themes:
- Platform and breakpoints:
- States drawn:
- Origin of the copy: user | plugin-ux-writing | agreed labels, final copy still missing
- SVG: `<NNN>-mock-<topic>-<screen>.svg`
```

## Example

Mock of payment in the light theme, with the shop kit's action color and type. The error state uses the kit's error color, the notice "The charge did not go through" if `plugin-ux-writing` already gave it, and the card fields stay filled. The path to the result is in the accepted user flow; this mock does not link it.

## Prerequisites

- **Task.** An `accepted` task analysis, or the task in this turn. If neither exists, write it in this turn with template `single-task`. State: `accepted`. Change it with `/uiux-tasks`. Regenerate this mock with `/uiux-mock`.
- **Path.** An `accepted` user flow, or the path in this turn. If neither exists, write the user flow in this turn with template `linear-three`: the screens named in the request, in that order; one screen becomes that screen then a result, and the error returns to it with the data kept; no screen named becomes form, wait, result. A payment or an irreversible action (pay, delete, send, publish, buy, transfer) inserts a confirm screen before the result. State: `accepted`. Change it with `/uiux-user-flow`. Regenerate this mock with `/uiux-mock`.
- **UI kit.** An `accepted` kit, a named preset, or the tokens in this turn. If none of these arrive, write preset `plain` with `define-appearance` and then the mock. State: `accepted`. Change it with `/uiux-ui-kit`. Regenerate this mock with `/uiux-mock`. Do not invent a palette.

## Prompts

In one message:

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit: preset plain. Other presets: dense, material-3, hig, fluent-2.
```

The UI kit is not in this order. When it is missing, preset `plain` is written with the mock.

In order, omitting the ones already met:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

```text
/uiux-user-flow for pay with a card.
The task is pay with a card.
Screens: cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

```text
/uiux-mock of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
```

## Done

- The path is an accepted user flow, the path in this turn, or template `linear-three` written in this turn. The UI kit line names an accepted kit, a preset id, or tokens from this turn. If none was selected, the kit is preset `plain`, written by `define-appearance` before this file. No palette was invented. Each template used is under Assumed.
- Themes are only the ones the product has. States that change the appearance are drawn. Error keeps what was typed and shows what failed.
- Copy comes from the user, from `plugin-ux-writing`, or from agreed labels, and the origin line says which. No new microcopy.
- The SVG uses kit colors. There are no redlines and no links to other screens.
