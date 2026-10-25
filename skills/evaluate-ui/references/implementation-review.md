# Implementation review

It has no standard of its own. The criterion is the `accepted` handoff and the `accepted` UI kit. The mock is also looked at when the handoff points at it.

## What it fixes

Differences between the built screen and what was specified: measures, tokens, states, breakpoints, and copy.

## What it does not do

It does not verify the use case. It does not verify WCAG: that is asked of `adrenaline-accessibility`. It does not fix the code.

## How to do it

1. The built screen arrives as a screenshot or as a URL. If they give a URL, open that screen. If you cannot open it, ask for a screenshot and leave the delivery `proposed`.
2. Compare against the handoff. If there is no `accepted` handoff, compare with what does exist (mock, kit) and leave the delivery `proposed`, saying what was missing.
3. Check measures, tokens, states, breakpoints, and copy. Copy that differs from the handoff is a finding, even when it "can be understood". The origin of the copy is `adrenaline-ux-writing` or the user; do not rewrite the copy here.
4. Each difference says the element, what was specified, what was built, and the correction (return to the handoff, or amend the handoff if what was built was a new decision).
5. Ask `adrenaline-accessibility` to audit the implementation.

## Template

```markdown
# Implementation review — <screen>

- Seen: screenshot | URL
- Handoff:
- UI kit:
- Mock:
- State of this delivery: accepted | proposed (missing: )
- Source: the handoff and the UI kit. It does not cover the use case or WCAG.

| Element | Specified | Built | Correction |
| --- | --- | --- | --- |

Accessibility: ask `adrenaline-accessibility` for the audit.
```

## Example

The handoff separates the amount and the form with `space.stack` (16 px). The screenshot shows about 8 px. Correction: use 16 px. The error states are not in the screenshot: they are noted as not checked and asked for, not treated as fine.

## Prerequisites

- **Handoff.** An `accepted` handoff. If there is only a mock or a kit, the review stays `proposed`. Does not stop the delivery: the delivery stays `proposed`. Earlier command: `/uiux-handoff`.
- **Screenshot or URL.** The built screen, in this turn. Stops the delivery. No earlier command.

## Prompts

In one message:

```text
/uiux-implementation-review of payment.
URL or screenshot: <paste it>.
Criterion: the accepted payment handoff.
```

In order, omitting the ones already met:

```text
/uiux-handoff of the payment screen.
The task is pay with a card.
The path is cart, payment, result. If the charge fails, it returns to payment with the data still filled in.
UI kit, light theme: action #0066cc, background #ffffff, text #1a1a1a, error #b00020, type Source Sans 3, space 16 px, radius 4 px, shadow 0 2 px 8 px.
```
