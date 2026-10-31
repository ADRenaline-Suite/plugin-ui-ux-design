# Changelog

## [0.0.1] - 2026-10-28

The version stays at 0.0.1 until the maintainer declares this plugin ready for distribution. The notes below record the work. They are not separate releases. Git tags `v0.1.0` and `v1.0.0` already exist and are left as they are.

### 2026-10-31

#### Added

- The output folder keeps `ORIGIN.json` (`suite`, `plugin`, `repository`, `convention` `adr-001`) so another agent can see which ADRenaline plugin wrote it. It is not an `<NNN>` file and it has no row in `STATUS.md`.

### 2026-10-29

#### Added

- `README.es.md` repeats this README in Spanish. Both files open with the language switch from ADR 4. Skills, commands, and rules stay English.
- Each `SKILL.md` and each reference manual has a Spanish sibling (`SKILL.es.md`, `<name>.es.md`) with the same switch. The agent still reads only the English file.

### 2026-10-28

#### Changed

- A missing design input no longer stops the command. The piece is written with a named template (`single-task`, `linear-three`, `plain`, `task-blocks`, `one-group`, `web`, `open`, `nielsen-5`, and the ones that stay `proposed`: `role-from-task`, `complete-the-task`, `task-unsupported`, `finish-unaided`, `neutral`). The file records it under Assumed, and the reply says it was taken automatically, which command changes it, and which command regenerates the piece.
- Consistency without a product UI kit, and an implementation review without a screenshot or a URL, still write nothing. Consistency does not compare against preset `plain`. Copy, accessibility notes, test rows, HEART figures, and a decision that was not made stay blank and `proposed`.
- `/uiux-help` prints each name as a link to that file on GitHub, and groups the commands under their skill. The sentences follow the language of the request.
- `/uiux-help` opens with what the plugin does, then Commands, Skills, Rules, Output, and Not in this plugin. Output links the plugin repository. Not in this plugin links a plugin only when its GitHub repository exists.
- The catalog shows `ADRenaline UI/UX Design`, not the repository name. Other plugins in Not in this plugin use the same kind of name.
- `/uiux-help` followed by other names explains those names and does not run them. Alone, it still prints the full catalog.

#### Added

- The README explains each command in plain language: what the piece is, why someone would ask for it, and which skill it belongs to. The one-line catalog in `/uiux-help` stays one line.
- Each skill and each piece manual opens with a breadcrumb back to the README and to its skill. The README link starts with a home icon. Piece tables link to those manuals, so the preview can be walked in both directions.
- Each skill, and each situation in its reference, has a `## Done` list. The command evaluates both before it closes. A failed item is fixed in the same turn, or the file is not left `accepted`. A gap the reference leaves as `proposed` stays `proposed`.

### 2026-10-25

#### Added

- Five UI kit presets in `skills/define-appearance/references/presets/`: `plain` (default), `dense`, `material-3`, `hig`, and `fluent-2`. When no kit is selected, `plain` is written and the other four are named. An accepted kit, or values given in the turn, still win. Consistency does not fill a missing kit with `plain`.

#### Changed

- The plugin id is `plugin-ui-ux-design`. It was `adrenaline-ui-ux-design`. The repository is https://github.com/ADRenaline-Suite/plugin-ui-ux-design. Cursor commands stay `/uiux-…`. In Claude Code the prefix is `/plugin-ui-ux-design:`.
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

### 2026-10-24

#### Added

- Skill `understand-user`: tasks, journey map, and brief. Released as `entender-usuario`.
- Skill `specify-screen`: sketch, wireframe, mock, prototype, and handoff. Released as `concretar-pantalla`.
- Skill `arrange-screens`: user flow, wireflow, and sitemap. Released as `ordenar-pantallas`.
- Skill `define-appearance`: moodboard and UI kit (DTCG 2025.10 tokens). Released as `definir-apariencia`.
- Skill `evaluate-ui`: heuristics, cognitive walkthrough, consistency, flow review, and implementation review. Released as `evaluar-ui`.
- Skill `test-with-users`: plan and analysis of a usability test, card sorting, tree testing, and HEART. Released as `medir-con-usuarios`.
- Skill `record-decision`: a design decision with state `proposed`, `accepted`, `deprecated`, or `superseded`. Released as `registrar-decision`.
- Rules `output-folder` and `ui-fidelity` (released as `fidelidad-ui`). Each restriction is also in the skill that applies it.
- Commands `/uiux-help` and one per piece. Delivery goes to `ui-ux-design/` (or to `outputDirs["plugin-ui-ux-design"]`), with a monotonic `<NNN>` and `STATUS.md`.
- Cursor and Claude Code manifests, so the repo installs with `claude plugin marketplace add ADRenaline-Suite/plugin-ui-ux-design`.

#### Changed

- The command prefix is `uiux` (`/uiux-help`, `/uiux-wireframe`, …), so the prefix matches the plugin name.
