---
name: uiux-help
description: "ADRenaline. Help: catalog of plugin-ui-ux-design (skills, rules, commands)."
---

# Help — plugin-ui-ux-design

Print this catalog as the reply. Do not run any skill or command. Do not invent entries that are not listed. If a component was added to the plugin and is missing here, add one line from its frontmatter `description` and say the catalog was refreshed.

Write the sentences in the language of the request. Keep command names, file ids, and every URL unchanged. Every id is a markdown link to the GitHub URL on its line. Do not print an id as plain text.

Keep the section headings. Under Commands, group the lines by the skill named in the line. Each group opens with that skill name linked to its SKILL.md. One line per item: the linked id, then the sentence.

## Plugin

- [**plugin-ui-ux-design**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/README.md) — Designs the experience and the interface of screens, from the task through handoff and evaluation, without writing the code.

## Skills

- [**understand-user**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/understand-user/SKILL.md) — Analyzes the user's tasks, builds the journey map, and closes the design brief before any screen is drawn.
- [**specify-screen**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/SKILL.md) — Produces the sketch, wireframe, mock, prototype, or handoff of a screen, from least to most concrete.
- [**arrange-screens**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/arrange-screens/SKILL.md) — Arranges the screens of a task into a user flow, a wireflow, or a sitemap.
- [**define-appearance**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/define-appearance/SKILL.md) — Sets the visual direction of the interface in a moodboard and the UI kit with its tokens. If no kit is selected, the plain preset is used.
- [**evaluate-ui**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/SKILL.md) — Evaluates an interface without users through heuristics, a cognitive walkthrough, consistency with the UI kit, a flow review, or an implementation review.
- [**test-with-users**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/SKILL.md) — Plans and analyzes a usability test, a card sort, a tree test, or HEART metrics.
- [**record-decision**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/record-decision/SKILL.md) — Records a design decision with its context, the options, the decision, and the consequences.

## Rules

- [**output-folder**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/rules/output-folder.mdc) — Every file goes in `ui-ux-design/` (or in `outputDirs["plugin-ui-ux-design"]` of `.cursor/adrenaline.json`). The artifact follows the language of the request.
- [**ui-fidelity**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/rules/ui-fidelity.mdc) — A missing design input uses a named template and is recorded as assumed. Consistency without a product kit, and an implementation review without a built screen, still stop.

## Commands

- [**/uiux-help**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/README.md) — This help (one-line catalog of the plugin).
- [**/uiux-tasks**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/understand-user/references/tasks.md) — Task analysis (skill understand-user): the person's goal, the tasks, the steps, and the order, before any screen is drawn.
- [**/uiux-journey-map**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/understand-user/references/journey-map.md) — Journey map (skill understand-user): one person's path through a scenario, with actions, thoughts, emotions, and opportunities, without proposing the interface.
- [**/uiux-brief**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/understand-user/references/brief.md) — Design brief (skill understand-user): the problem, who it is for, the constraints, and the measurable success criteria, before the form of the interface is chosen.
- [**/uiux-sketch**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/references/sketch.md) — Sketch (skill specify-screen): the idea of a screen and its blocks (named zones), without measure, color, or final copy.
- [**/uiux-wireframe**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/references/wireframe.md) — Wireframe (skill specify-screen): hierarchy and layout of a screen by window size, without brand color or a final typeface.
- [**/uiux-mock**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/references/mock.md) — Mock (skill specify-screen): the visual appearance of a screen with the UI kit tokens, without the path or the specification for building it.
- [**/uiux-prototype**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/references/prototype.md) — Prototype (skill specify-screen): linked screens for walking a task in the browser, without measures or accessibility requirements.
- [**/uiux-handoff**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/specify-screen/references/handoff.md) — Handoff (skill specify-screen): measures, states, copy, behavior by window size, and accessibility, so the screen can be built without guessing.
- [**/uiux-user-flow**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/arrange-screens/references/user-flow.md) — User flow (skill arrange-screens): the path between screens to complete a task, with decisions and returns, without the layout of each screen.
- [**/uiux-wireflow**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/arrange-screens/references/wireflow.md) — Wireflow (skill arrange-screens): the same path of a task, with the hierarchy of each step in view, without color or build measures.
- [**/uiux-sitemap**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/arrange-screens/references/sitemap.md) — Sitemap (skill arrange-screens): which screens exist and how they are grouped, without the path of a task or the look of each screen.
- [**/uiux-moodboard**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/define-appearance/references/moodboard.md) — Moodboard (skill define-appearance): visual direction (references, color, type, and tone) on sample screens, before tokens and components are fixed.
- [**/uiux-ui-kit**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/define-appearance/references/ui-kit.md) — UI kit (skill define-appearance): components, tokens (color, typography, space, radius, and elevation), and rules for repeating the design, with presets plain (default), dense, material-3, hig, and fluent-2.
- [**/uiux-heuristics**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/references/heuristics.md) — Heuristic evaluation (skill evaluate-ui): usability problems visible on a screen, with the heuristic, the place, the severity, and the correction.
- [**/uiux-cognitive-walkthrough**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/references/cognitive-walkthrough.md) — Cognitive walkthrough (skill evaluate-ui): whether someone who knows the task, and does not know this interface, can take each step by exploring.
- [**/uiux-consistency**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/references/consistency.md) — Consistency (skill evaluate-ui): where a screen drifts from the UI kit's components and tokens.
- [**/uiux-flow-review**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/references/flow-review.md) — Flow review (skill evaluate-ui): problems in the path of a task, without judging the look or the code.
- [**/uiux-implementation-review**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/evaluate-ui/references/implementation-review.md) — Implementation review (skill evaluate-ui): differences between the built screen and the handoff in measures, tokens, states, window sizes, and copy.
- [**/uiux-usability-test**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/references/usability-test.md) — Usability test plan (skill test-with-users): scenario tasks, who takes part, what to observe, and how to record it, without running the session or calculating results.
- [**/uiux-test-analysis**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/references/test-analysis.md) — Usability test analysis (skill test-with-users): success rate per task, time, problems by severity, and the SUS score if there was one.
- [**/uiux-card-sorting**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/references/card-sorting.md) — Card sorting (skill test-with-users): a plan for how people group content and, when there is data, the groups that came out, without evaluating a sitemap that already exists.
- [**/uiux-tree-testing**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/references/tree-testing.md) — Tree testing (skill test-with-users): a plan and an analysis of whether people find a destination in the sitemap, without the visual appearance of the screen.
- [**/uiux-heart**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/test-with-users/references/heart.md) — HEART metrics (skill test-with-users) for a product already launched: experience goal, signal, and metric (attitude, engagement, adoption, return, and task success).
- [**/uiux-decision**](https://github.com/ADRenaline-Suite/plugin-ui-ux-design/blob/main/skills/record-decision/references/decision.md) — Design decision (skill record-decision): the context, the options, the decision, and the consequences, and whether that decision governs.

## Output

- Folder: `ui-ux-design/` (override via `.cursor/adrenaline.json`).
- Name: `<NNN>-<type>-<topic>.<ext>`, with monotonic `<NNN>`. The prose follows the language of the request. The type stays the English piece id.

| Format | Description |
| --- | --- |
| `.md` | Specification of the piece. User flow and sitemap include Mermaid. |
| `.svg` | Sketch, wireframe, mock, prototype, handoff, moodboard, and wireflow, one per screen. |
| `.tokens.json` | UI kit tokens in DTCG 2025.10. |
| `.csv` | Test observations, SUS answers, card sorting, and tree testing. |
| `STATUS.md` | State of each file. Columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`. |

## Not in this plugin

- UML diagrams → `plugin-uml-diagrams`.
- WCAG audit and accessibility notes → `plugin-accessibility`.
- Interface copy → `plugin-ux-writing`.
- Use case → `plugin-project-manager`.
- Test scenario → `plugin-qa-engineer`.
- Interface code, instrumentation, and Core Web Vitals → frontend area.

In Claude Code, commands use the prefix `/plugin-ui-ux-design:` (example: `/plugin-ui-ux-design:uiux-help`).

## Done

- The reply is this catalog. Every id is a markdown link to the GitHub URL listed here. Commands are grouped by skill.
- No skill ran. No command ran. No file was written.
- No entry was invented. If a component exists in the plugin and is missing here, one line was added from its `description` and the reply says the catalog was refreshed.
