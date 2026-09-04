# Stress testing

Stress testing checks whether one component survives the content, states and
environments it can actually receive. It observes failures; it does not invent
visual preferences.

## Scope one component

Choose one component or one tightly bounded surface. Record its inputs, slots,
states, container assumptions and production data shape. If several components
are named, select the one that carries the task or run separate scopes.

## Select scenarios by cue

Keep only scenario axes supported by the component:

| Axis | Keep it when the component has | Example scenarios |
| --- | --- | --- |
| Content length | User, API, CMS or translated text | Empty, typical, several lines, unbreakable string |
| Content shape | User-controlled or localized content | Emoji, diacritics, RTL and mixed direction |
| Quantity | Repeated items | Zero, one, realistic count and a large count |
| Container | Any responsive container | Narrow, squeezed sibling and wide container |
| State | Explicit state or lifecycle | Loading, error, disabled, selected and busy |
| Environment | Supported modes | Zoom, dark theme, reduced motion and high contrast |

Drop an axis that has no cue and say why. Do not run every possible matrix
combination when a smaller set can expose the failure.

## Use realistic fixtures

Use real product-shaped strings, representative item counts and actual component
props. Add deliberately hostile inputs only when they are valid production
possibilities or when the purpose of the test is explicitly robustness beyond
normal data.

Do not use a rebuilt lookalike. The component under test must run in the
project's actual styling, font, semantics and state environment where the
request requires runtime evidence.

## Observe

Look for concrete failures:

- clipping, overflow, overlap or unexpected scroll;
- controls losing their name, focus or keyboard path;
- hierarchy or recovery becoming unclear;
- layout shift, unstable numbers or broken directionality;
- text or status losing meaning in a theme or motion mode;
- loading, empty or error states hiding the next action;
- performance or input problems when quantity is large.

Phrase findings as observations tied to a scenario. "The 70-character label
escapes the control at 320px" is evidence. "The card feels cramped" is a
preference until a task or layout failure is identified.

## Artifact boundary

A temporary page, fixture or harness is a mutation. Create it only after an
explicit request, isolate it from production imports, state where it lives and
state how it will be cleaned up. If the environment cannot render it, hand over
the artifact or mark runtime observations `Not verified`; do not simulate a
browser result.

## Verification

Record the scenarios rendered, the environment conditions and the observed
result for each. An unrendered scenario can produce a test plan or hypothesis,
not a confirmed finding. After an authorized fix, rerun the failing scenario
and verify that the original failure is gone without breaking the shared floor.
