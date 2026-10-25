# Card sorting

Source: Nielsen Norman Group, Card Sorting. It generates groupings. It does not evaluate a hierarchy that is already named: that is tree testing.

## What it fixes

The session plan and, when there is data, how people grouped the cards.

## How to do it

1. The user states the kind. Open: the person creates the groups and names them. Closed: the groups already have names. Hybrid: there are given groups and the person may create others. If they do not say, ask.
2. The cards are the contents the user lists. Do not add "typical" contents.
3. The plan states participant criteria, the number the user gave, and that a person runs the session.
4. With data, the CSV is `participant,card,group,kind`. `kind` is `open`, `closed`, or `hybrid`. The Markdown summarizes agreements (cards that land together) and group names that repeat. A disagreement is counted, not broken by inventing the "correct group". Prose follows the language of the artifact.
5. Proposing the new grouping as a sitemap is another delivery (`arrange-screens`) or a decision (`record-decision`). This file does not replace the sitemap.
6. If there is only a plan, the CSV carries the header and the delivery is `accepted`. If they asked for the analysis and there are no rows, it stays `proposed`.

## Template

```markdown
# Card sorting — <topic>

- Kind: open | closed | hybrid
- Cards:
- Given groups: <closed or hybrid only>
- Participants:
- Source: Nielsen Norman Group, Card Sorting.

## Agreements

| Cards that match | Most frequent group | How many participants |
| --- | --- | --- |

CSV: `<NNN>-card-sorting-<topic>.csv` (`participant,card,group,kind`).
```

## Example

Open, cards "receipt", "card", "address". Three people put receipt and card together and call them "Payment". That is reported as an agreement. The sitemap is not rewritten in this file.

## Prerequisites

- **Kind.** Open, closed, or hybrid, in this turn. Stops the delivery. No earlier command.

## Prompts

In one message:

```text
/uiux-card-sorting of the shop.
Kind: open.
Cards: receipt, card, address.
```

There is no earlier command. The single prompt is the way.
