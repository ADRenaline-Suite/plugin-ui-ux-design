---
name: uiux-help
description: "ADRenaline. Help: catalog of adrenaline-ui-ux-design (skills, rules, commands)."
---

# Help — adrenaline-ui-ux-design

Print this catalog as the reply. One line per item. Do not run any skill or command. Do not invent entries that are not listed. If a component was added to the plugin and is missing here, add one line from its frontmatter `description` and say the catalog was refreshed.

## Plugin

- **adrenaline-ui-ux-design** — Diseña la experiencia y la interfaz de las pantallas, de la tarea al handoff y a la evaluación, sin escribir el código.

## Skills

- **entender-usuario** — Analiza tareas, journey map y brief antes de dibujar pantallas.
- **concretar-pantalla** — Produce sketch, wireframe, mock, prototype y handoff de una pantalla.
- **ordenar-pantallas** — Ordena pantallas en user flow, wireflow y sitemap.
- **definir-apariencia** — Fija el moodboard y el UI kit con sus tokens.
- **evaluar-ui** — Evalúa sin usuarios: heurísticas, recorrido cognitivo, consistencia, flujo e implementación.
- **medir-con-usuarios** — Planea y analiza test de usabilidad, card sorting, tree testing y HEART.
- **registrar-decision** — Registra una decisión de diseño con su estado.

## Rules

- **output-folder** — Todo archivo va en `ui-ux-design/` (o en `outputDirs["adrenaline-ui-ux-design"]` de `.cursor/adrenaline.json`).
- **fidelidad-ui** — No salta de fidelidad, no deja una pantalla sin estados y no hace aquí el oficio de otro plugin.

## Commands

- **/uiux-help** — Este help (catálogo de una línea del plugin).
- **/uiux-tareas** — Análisis de tareas del usuario.
- **/uiux-journey-map** — Journey map de una persona y un escenario.
- **/uiux-brief** — Brief de diseño.
- **/uiux-sketch** — Sketch de una pantalla.
- **/uiux-wireframe** — Wireframe de una pantalla.
- **/uiux-mock** — Mock de una pantalla.
- **/uiux-prototype** — Prototype enlazado de un recorrido.
- **/uiux-handoff** — Handoff de una pantalla.
- **/uiux-user-flow** — User flow de una tarea.
- **/uiux-wireflow** — Wireflow de una tarea.
- **/uiux-sitemap** — Sitemap de las pantallas.
- **/uiux-moodboard** — Moodboard de la interfaz.
- **/uiux-ui-kit** — UI kit y tokens de la interfaz.
- **/uiux-heuristicas** — Evaluación heurística de una pantalla.
- **/uiux-recorrido-cognitivo** — Recorrido cognitivo de una tarea.
- **/uiux-consistencia** — Consistencia de una pantalla con el UI kit.
- **/uiux-revision-flujo** — Revisión del flujo de una tarea.
- **/uiux-revision-implementacion** — Revisión de la implementación contra el handoff.
- **/uiux-test-usabilidad** — Plan de un test de usabilidad.
- **/uiux-analisis-test** — Análisis de un test de usabilidad.
- **/uiux-card-sorting** — Plan y análisis de card sorting.
- **/uiux-tree-testing** — Plan y análisis de tree testing.
- **/uiux-heart** — Métricas HEART de un producto lanzado.
- **/uiux-decision** — Decisión de diseño.

## Output

- Folder: `ui-ux-design/` (override via `.cursor/adrenaline.json`).
- Name: `<NNN>-<tipo>-<tema>.<ext>`, with monotonic `<NNN>`.

| Format | Description |
| --- | --- |
| `.md` | Especificación de la pieza. User flow y sitemap llevan Mermaid. |
| `.svg` | Sketch, wireframe, mock, prototype, handoff, moodboard y wireflow, uno por pantalla. |
| `.tokens.json` | Tokens del UI kit en DTCG 2025.10. |
| `.csv` | Observaciones del test, respuestas SUS, card sorting y tree testing. |
| `STATUS.md` | Estado de cada archivo. |

## Not in this plugin

- Diagramas UML → `adrenaline-uml-diagrams`.
- Auditoría WCAG y anotaciones de accesibilidad → `adrenaline-accessibility`.
- Textos de la interfaz → `adrenaline-ux-writing`.
- Caso de uso → `adrenaline-project-manager`.
- Escenario de prueba → `adrenaline-qa-engineer`.
- Código de la interfaz, instrumentación y Core Web Vitals → área de frontend.

In Claude Code, commands use the prefix `/adrenaline-ui-ux-design:` (example: `/adrenaline-ui-ux-design:uiux-help`).
