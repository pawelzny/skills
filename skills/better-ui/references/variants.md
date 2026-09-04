# Variants

Variants are a decision tool, not a collection of cosmetic recolors. Build them
only when the user explicitly wants alternatives and the decision has a clear
surface, task and evaluation axis.

## Frame the decision

Before creating candidates, record:

- the component or flow being varied;
- the user task it supports;
- the primary axis of difference;
- fixed product, accessibility and technical constraints;
- the evidence or question the comparison should answer;
- the host page, realistic data and supported conditions.

Good axes include structure, density, emphasis, typography or voice. A variant
should have a different answer to the same brief, not just a different hue.

## Build a small set

Default to three directions. Name each by its position on the chosen axis, such
as `Quiet`, `Dense` or `Editorial`, rather than `Option A`. Change one primary
axis at a time so the result teaches what caused the difference. Secondary
changes may follow coherently from that axis.

All candidates share a non-negotiable floor:

- accessible names and semantic controls;
- keyboard reachability and visible focus;
- no clipping at supported narrow widths;
- no meaning conveyed by color alone;
- product and platform constraints;
- the same required states and content model.

Do not trade this floor for visual novelty.

## Use real context

Prefer the page that will contain the component, with real neighboring controls,
real tokens and realistic data. If that page is unavailable, make the smallest
isolated fixture that states the missing context. Include long, empty, error,
loading and selected states when they can change the decision.

A thumbnail, lorem ipsum and a blank canvas conceal the very trade-offs the
variants are meant to expose.

## Compare without bias

Before presenting the set, verify that each candidate renders and that its
interactions respond. Report the conditions inspected. Then compare:

| Variant | Axis position | Best when | Cost or risk |
| --- | --- | --- | --- |
| Named direction | What changed | Task or context that favors it | What it sacrifices |

Do not mark a personal favorite as the answer. Recommend one only when the
user's task, product constraints and evidence support it. Otherwise state the
decision that remains with the user and the experiment that would resolve it.

## Promotion and cleanup

When the user chooses a direction, implement it in the proper production
location only if implementation was requested. Remove or isolate unchosen
candidates and their fixtures according to the agreed cleanup condition. Never
silently merge exploratory code into production.

## Verification

Check every candidate against the shared accessibility floor, realistic content,
supported widths and required states. Record which conditions were not tested as
`Not verified`. A candidate that was never rendered is a proposal, not an
observed variant.
