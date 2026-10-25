# Changelog

## [1.0.0] - 2026-10-25

### Changed

- The plugin is written in English. The artifact follows the language of the request. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Skills and commands with Spanish names are renamed. The old names no longer exist.

| Before | After |
| --- | --- |
| `entender-usuario` | `understand-user` |
| `concretar-pantalla` | `specify-screen` |
| `ordenar-pantallas` | `arrange-screens` |
| `definir-apariencia` | `define-appearance` |
| `evaluar-ui` | `evaluate-ui` |
| `medir-con-usuarios` | `test-with-users` |
| `registrar-decision` | `record-decision` |
| `fidelidad-ui` | `ui-fidelity` |
| `/uiux-tareas` | `/uiux-tasks` |
| `/uiux-heuristicas` | `/uiux-heuristics` |
| `/uiux-recorrido-cognitivo` | `/uiux-cognitive-walkthrough` |
| `/uiux-consistencia` | `/uiux-consistency` |
| `/uiux-revision-flujo` | `/uiux-flow-review` |
| `/uiux-revision-implementacion` | `/uiux-implementation-review` |
| `/uiux-test-usabilidad` | `/uiux-usability-test` |
| `/uiux-analisis-test` | `/uiux-test-analysis` |

- The README has the diagram and the prerequisite table for each command.
- If a stopping prerequisite is missing, the command does not write the piece: it names what is missing, gives one prompt, and lists the earlier commands in order. For the mock, the UI kit is one of those prerequisites.
- `/uiux-help` shows each command as a link to its manual on GitHub.
- Each command `description` names the piece and says what it fixes, so the command picker is readable without knowing the term. `/uiux-help` repeats that sentence.
- The README, each command `description`, and `/uiux-help` name the skill of that piece. The prerequisite diagram groups the commands by skill.

## [0.1.0] - 2026-10-24

### Added

- Skill `understand-user`: tasks, journey map, and brief. Released as `entender-usuario`.
- Skill `specify-screen`: sketch, wireframe, mock, prototype, and handoff. Released as `concretar-pantalla`.
- Skill `arrange-screens`: user flow, wireflow, and sitemap. Released as `ordenar-pantallas`.
- Skill `define-appearance`: moodboard and UI kit (DTCG 2025.10 tokens). Released as `definir-apariencia`.
- Skill `evaluate-ui`: heuristics, cognitive walkthrough, consistency, flow review, and implementation review. Released as `evaluar-ui`.
- Skill `test-with-users`: plan and analysis of a usability test, card sorting, tree testing, and HEART. Released as `medir-con-usuarios`.
- Skill `record-decision`: a design decision with state `proposed`, `accepted`, `deprecated`, or `superseded`. Released as `registrar-decision`.
- Rules `output-folder` and `ui-fidelity` (released as `fidelidad-ui`). Each restriction is also in the skill that applies it.
- Commands `/uiux-help` and one per piece. Delivery goes to `ui-ux-design/` (or to `outputDirs["adrenaline-ui-ux-design"]`), with a monotonic `<NNN>` and `STATUS.md`.
- Cursor and Claude Code manifests, so the repo installs with `claude plugin marketplace add d-mente/adrenaline-ui-ux-design`.

### Changed

- The command prefix is `uiux` (`/uiux-help`, `/uiux-wireframe`, …), so the prefix matches the plugin name.
