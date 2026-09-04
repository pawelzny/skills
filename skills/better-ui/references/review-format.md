# Review format

Use this contract for a complete audit or recommendation. A shorter request
may use a compact version, but it must preserve scope, evidence, impact and
verification.

## Scope block

Start with:

| Field | Value |
| --- | --- |
| Mode | `AUDIT`, `RECOMMEND`, `CHANGE REVIEW`, `STRESS TEST`, `VARIANTS` or `EXPLAIN` |
| User and task | Who is doing what |
| Scope | Screen, component, flow, change or effect |
| Non-goals | Explicit exclusions |
| Local sources | Product requirements, design system, tokens and conventions inspected |
| Evidence route | Source, runtime, image, version control or user evidence |
| Conditions | Viewport, data, state, theme, direction and motion settings |
| Limits | Missing evidence and uninspected surfaces |

Do not call an entire repository reviewed when only one surface was inspected.

## Coverage

List each relevant domain:

| Domain | Evidence inspected | Result |
| --- | --- | --- |
| UX framing | User, task, outcome and constraints | Findings, `Clear` or `Not reviewed` |
| Accessibility | Semantics, keyboard, focus, names and states | Findings, `Clear` or `Not reviewed` |
| Layout | Hierarchy, order, responsive behavior and localization | Findings, `Clear` or `Not reviewed` |
| Writing | Labels, terminology, errors and empty states | Findings, `Clear` or `Not reviewed` |
| Typography | Font, scale, wrapping, truncation and direction | Findings, `Clear` or `Not reviewed` |
| Color | Semantics, rendered contrast and themes | Findings, `Clear` or `Not reviewed` |
| UI polish | Surfaces, icons, motion and performance | Findings, `Clear` or `Not reviewed` |

`Clear` means inspected with no actionable finding. `Not reviewed` names why.

## Findings

Use one row per root cause and list repeated locations together:

| Severity | Domain | Status | Location | Before | After | Why and evidence |
| --- | --- | --- | --- | --- | --- | --- |
| HIGH | Accessibility | Introduced | `path:line` | Current behavior | Actionable replacement | Principle, user impact and evidence tier |

Status is required for change review and omitted for a non-change audit:

- `Introduced`: the change created the issue;
- `Regression`: the change weakened behavior that was previously correct;
- `Pre-existing`: present but not caused by the reviewed change.

Severity:

- `HIGH`: blocks a task, hides content or controls, misleads the user, creates
  data-loss risk or causes a repeated systemic failure;
- `MEDIUM`: meaningfully harms comprehension, efficiency, adaptability or
  consistency;
- `LOW`: isolated polish with limited task impact.

Do not report taste as a finding. Do not downgrade a confirmed accessibility or
interaction blocker because the visual surface is small. Do not turn an
unverified hypothesis into a finding; make it a validation item instead.

## Recommendations

After findings, provide the ordered recommendation:

1. the chosen change;
2. the reason it best fits the task and evidence;
3. the implementation boundary;
4. the trade-off or cost;
5. the condition that would make it the wrong choice;
6. the first validation step.

Compare alternatives when the decision is material. If evidence is too weak to
choose, say what is missing and mark the recommendation `Provisional`.

## Verification

Separate performed checks from gaps:

| Check | Method or interaction | Result |
| --- | --- | --- |
| Performed | Exact condition and observed output | Pass or finding |
| Not verified | Why the environment could not perform it | Follow-up needed |

For a change review, include the resolved base and head, changed files,
excluded/generated files and consumer expansion bound. For a temporary artifact,
include its location and cleanup condition.

## Verdict

Use:

- `Block` when a confirmed `HIGH` finding remains;
- `Approve` only when required coverage was inspected and no confirmed `HIGH`
  finding remains;
- `Provisional` when a material decision depends on unverified evidence.

A verdict is about the stated scope, not the whole product.
