# Design decision

Source: Michael Nygard, Documenting Architecture Decisions (2011). The title may say "design decision": the format is Nygard's.

## What it fixes

The context, the options considered, the decision, and the consequences. The state says whether it governs.

## How to do it

1. Context: what forces the decision (a finding, a platform constraint, a test). Cite the `<NNN>` of that artifact if it exists.
2. Options: at least two, with their cost. Include the one that was discarded.
3. Decision: the one the user made, in one sentence. If they have not chosen yet, the state is `proposed` and the decision says "pending".
4. Consequences: which delivery has to change (handoff, kit, flow) and what stays out.
5. Do not copy the handoff into the decision. Link it by file name.

## Template

```markdown
# <NNN> — <title>

- State: proposed | accepted | deprecated | superseded
- Supersedes: <N or none>
- Source: Michael Nygard (2011)

## Context

## Options

1. <option> — <consequence of choosing it>

## Decision

## Consequences
```

## Example

State: `accepted`. Context: the heuristics finding for payment on a network error (severity 3). Options: an empty error screen, or the notice over the form. Decision: the notice over the form, with the card intact. Consequences: amend the payment handoff; the user flow does not add a screen.

## Prerequisites

- **Decision.** Made by whoever asks for the record. If it is not made, the state is `proposed`. Does not stop the delivery: the delivery stays `proposed`. No earlier command.

## Prompts

In one message:

```text
/uiux-decision of retry on payment.
Decision made: the notice stays on the same screen and the card data is kept.
Options discarded: an empty error screen.
```

There is no earlier command. The single prompt is the way.
