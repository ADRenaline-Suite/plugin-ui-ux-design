[🏠 UI/UX Design](../../../README.md) / [Define the appearance](../SKILL.md)

# Presets

Five starters for the UI kit. They are what to recommend. The file that is saved is still a normal UI kit in the project folder.

`plain` and `dense` are this plugin's starters. They have no external standard. `material-3`, `hig`, and `fluent-2` copy the published guide named in their file. Where that guide does not publish a value the token format needs, the preset file says so. Do not fill that gap with a new value when delivering.

## Which one

| Id | Recommend when |
| --- | --- |
| `plain` | Web, no brand, comfortable reading. This is the default. |
| `material-3` | Android, or a product that already follows Material Design 3. |
| `hig` | iOS, iPadOS, or macOS. |
| `fluent-2` | Windows. |
| `dense` | A web tool with tables or a backoffice. Same color as `plain`, tighter type and space. |

## Rule

1. An `accepted` kit of the product wins. Do not replace it with a preset unless the person asks to replace that kit.
2. Color, type, space, radius, and elevation written in this turn win over a preset. Write those values. Do not correct them toward a preset.
3. A named preset is the values. Read `presets/<id>.md` and `presets/<id>.tokens.json`. Copy the token values into the delivery. Do not change a number, a name, or a hex. Translate the prose and each `$description` into the language of the request. The preset id stays in English.
4. If there is no `accepted` kit, no values in this turn, and no named preset, use `plain`. Record it under Assumed: template `plain`, because none was selected, and name the other four in the table order, each with its "recommend when" line. Change it with `/uiux-ui-kit`. Regenerate the kit with `/uiux-ui-kit`, and regenerate the mock or the handoff with that command if one was already drawn.
5. An unknown name is not a selection. Do not write the kit. Name the five and say `plain` is the one used when they do not choose.
6. Do not invent a sixth preset. These five are light only. Do not add a dark theme.
7. The mock and the handoff follow this same rule when they need a kit and do not have one: write the kit first, then the piece. Consistency does not. A review compares against the kit the screen already has. A missing kit stops that review. Do not judge a screen against `plain` just because no kit was selected.

Naming the platform is not naming a preset. "The app is on iOS" recommends `hig` in the reply and still writes `plain` until they name `hig`.

## Aliases

| They say | Preset |
| --- | --- |
| default, none | `plain` |
| material, material 3, m3 | `material-3` |
| apple, human interface, ios, macos | `hig` |
| fluent, fluent 2 | `fluent-2` |

## Files

| Preset | Manual | Tokens |
| --- | --- | --- |
| `plain` | [presets/plain.md](presets/plain.md) | `presets/plain.tokens.json` |
| `material-3` | [presets/material-3.md](presets/material-3.md) | `presets/material-3.tokens.json` |
| `hig` | [presets/hig.md](presets/hig.md) | `presets/hig.tokens.json` |
| `fluent-2` | [presets/fluent-2.md](presets/fluent-2.md) | `presets/fluent-2.tokens.json` |
| `dense` | [presets/dense.md](presets/dense.md) | `presets/dense.tokens.json` |

## Done

This file is not a situation. The delivery is the UI kit. Evaluate `## Done` in `ui-kit.md`. The preset copied there is the one this file selects, with its values unchanged.
