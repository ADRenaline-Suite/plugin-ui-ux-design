---
name: uiux-mock
description: "ADRenaline. Mock (skill specify-screen): the visual appearance of a screen with the UI kit tokens, without the path or the specification for building it."
---

Draw the mock of the screen.

1. Follow the skill `specify-screen` in this plugin.
2. This command fixes the piece. In that skill, read `references/mock.md`. Do not ask again which piece it is.
3. Prerequisites: task, path, UI kit. If any is missing, follow "When a prerequisite is missing" in that skill and the prompts in `references/mock.md`. If this turn brings the tokens and there is no `accepted` kit, write the kit with `define-appearance` before the mock.
