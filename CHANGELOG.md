# Changelog

## [Unreleased]

## [0.1.0] - 2026-10-24

### Added

- Skill `entender-usuario`: tareas, journey map y brief.
- Skill `concretar-pantalla`: sketch, wireframe, mock, prototype y handoff.
- Skill `ordenar-pantallas`: user flow, wireflow y sitemap.
- Skill `definir-apariencia`: moodboard y UI kit (tokens DTCG 2025.10).
- Skill `evaluar-ui`: heurísticas, recorrido cognitivo, consistencia, revisión del flujo y revisión de la implementación.
- Skill `medir-con-usuarios`: plan y análisis de test de usabilidad, card sorting, tree testing y HEART.
- Skill `registrar-decision`: decisión de diseño con estado `proposed`, `accepted`, `deprecated` o `superseded`.
- Rules `output-folder` y `fidelidad-ui`. Cada restricción está también en el skill que la aplica.
- Commands `/uiux-help` y uno por pieza. La entrega va a `ui-ux-design/` (o a `outputDirs["adrenaline-ui-ux-design"]`), con `<NNN>` monótono y `STATUS.md`.
- Manifiestos de Cursor y de Claude Code, para instalar el repo con `claude plugin marketplace add d-mente/adrenaline-ui-ux-design`.

### Changed

- El oficio de los commands es `uiux` (`/uiux-help`, `/uiux-wireframe`, …), para que el prefijo coincida con el nombre del plugin.
