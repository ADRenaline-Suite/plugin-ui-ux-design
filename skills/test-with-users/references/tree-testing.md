# Tree testing

Source: Nielsen Norman Group, Tree Testing. It evaluates a hierarchy that is already named. Direct success, indirect success, and the first click are the result.

## What it fixes

Whether people find a destination in the sitemap, without the visual appearance of the screen.

## How to do it

1. The hierarchy is an `accepted` sitemap or the tree the user pastes, with the names already decided. Do not rename items during the analysis.
2. Each task asks to find a destination and does not say which branch it is in. "Where do you see the order receipt?" is right. "Go into Account and then Receipts" is not.
3. The plan fixes participants as the user describes them. A person runs the session.
4. With data, the CSV is `participant,task,direct_success,indirect_success,first_click,path`. Successes and the first click are `yes` or `no`.
   - Direct success: they reached the destination without going back.
   - Indirect success: they reached the destination and did go back.
   - First click: the first item they chose is on a correct path to the destination.
5. A task cannot be both a direct and an indirect success. If the data arrives that way, ask.
6. The Markdown gives, per task, the share of each success and of the first click. Do not turn the tree into a new sitemap here.
7. If there is only a plan, the CSV carries the header and the delivery is `accepted`. If they asked for the analysis and there are no rows, it stays `proposed`.

## Template

```markdown
# Tree testing — <topic>

- Tree: <sitemap or list>
- Participants:
- Source: Nielsen Norman Group, Tree Testing.

## Tasks

1. <find a destination, without naming the branch>

## Results

| Task | Direct | Indirect | Correct first click |
| --- | --- | --- | --- |

CSV: `<NNN>-tree-testing-<topic>.csv` (`participant,task,direct_success,indirect_success,first_click,path`).
```

## Example

Tree: Shop → Order → Payment. Task: "Where do you check the receipt?". Of five people, two arrive without going back (direct 0.4), one arrives after going back (indirect 0.2), and three choose "Order" first (first click 0.6).

## Prerequisites

- **Tree.** An `accepted` sitemap, or the tree pasted in this turn. Stops the delivery. Earlier command: `/uiux-sitemap`.

## Prompts

In one message:

```text
/uiux-tree-testing of the receipt.
Tree: Shop → Order → Payment → Receipt.
Task: where do you check the receipt?
```

In order, omitting the ones already met:

```text
/uiux-sitemap of the shop.
Groups: Shop → Order → Payment → Receipt.
Payment covers the task pay with a card.
```
