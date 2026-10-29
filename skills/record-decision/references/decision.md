<p align="right">Language:&emsp;<img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-on.svg" align="middle" style="vertical-align:middle"> <a href="decision.es.md" style="vertical-align:middle"><img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-off.svg" align="middle" style="vertical-align:middle"></a></p>

[🏠 UI/UX Design](../../../README.md) / [Record a decision](../SKILL.md)

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

- **Decision.** Made by whoever asks for the record. If it is not made, write the file, leave the state `proposed`, and write the decision as pending. No template. Do not pick an option. The close says the decision was not made and that no option was chosen. Regenerate with `/uiux-decision` when the decision exists.

## Prompts

In one message:

```text
/uiux-decision of retry on payment.
Decision made: the notice stays on the same screen and the card data is kept.
Options discarded: an empty error screen.
```

There is no earlier command. The single prompt is the way.

## Done

- Context, at least two options (including the discarded one), the decision, and the consequences are present. The decision is the one the user made. If they have not chosen, the state is `proposed` and the decision says pending. The winning option was not picked by the skill.
- The state in the file and the `STATUS.md` row are the same. A replacement uses the next `<NNN>` and marks the previous row `superseded`.
- Consequences name which delivery changes. The handoff, the kit, and the flow were not rewritten in this file.
