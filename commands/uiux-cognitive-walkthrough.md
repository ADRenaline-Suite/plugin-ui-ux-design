---
name: uiux-cognitive-walkthrough
description: "ADRenaline. Cognitive walkthrough (skill evaluate-ui): whether someone who knows the task, and does not know this interface, can take each step by exploring."
---

Walk the task with a cognitive walkthrough.

1. Follow the skill `evaluate-ui` in this plugin.
2. This command fixes the piece. In that skill, read `references/cognitive-walkthrough.md`. Do not ask again which piece it is.
3. Prerequisites: task, steps. If either is missing, follow "When a prerequisite is missing" in that skill and the prompts in `references/cognitive-walkthrough.md`.

Before you close, evaluate `## Done` in that skill and in the reference this command names. Every item is true, or fix the delivery in this turn. Do not leave a file that fails an item. Do not mark it `accepted` while an item fails.
