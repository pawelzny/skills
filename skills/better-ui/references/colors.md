# Color

Color is a system of roles, states and themes, not a bag of attractive values.
Measure rendered pairs against the background they actually use and keep
semantic meaning separate from the primitive palette.

## Token structure

A maintainable color system commonly has two tiers:

- **Primitives:** raw hue or neutral values used to construct the system;
- **Semantic tokens:** roles such as surface, text, border, accent, success,
  warning and danger that components consume.

Reuse the project's notation. Do not introduce a second representation or add
an unused ramp to solve one local symptom. A semantic token should be chosen for
its role, not because its current value happens to look convenient.

## Meaning and redundancy

Use color consistently for the same interaction or state. Verify that status,
selection, progress, errors and affordances have a non-color cue where users
need one. A brand accent does not automatically mean interactive, and a status
color does not automatically mean decorative emphasis.

Multiple accents can be valid when they distinguish real categories or states.
"One accent" and "one primary action" are heuristics, not universal laws.

## Contrast measurement

Identify the foreground, opacity, compositing and actual background first. For
text over images, translucent surfaces or gradients, measure the worst relevant
region or provide a stable backing surface. Do not report a ratio or score that
was not calculated.

For formal accessibility claims, apply the relevant WCAG 2.x criterion and its
exceptions. APCA can be used as an additional design signal when the project
chooses it, but it must not silently replace the formal criterion.

Keep these concerns separate:

- accessibility determines whether a pair must pass;
- color review measures the rendered pair;
- product design decides whether and how a failing pair should be changed.

## Palette and themes

For a new system, perceptual color spaces can make ramp construction easier,
but gamut, fallbacks and browser support still matter. Preserve the project's
color notation when extending an existing system. Test light, dark, high-
contrast and custom themes independently rather than mechanically reversing a
palette.

A color fix should preserve semantic meaning. Changing lightness is often a
good first experiment, but hue, saturation, compositing and adjacent colors can
also affect the result. Remeasure after every change.

## Verification

Inspect token definitions and semantic usage. Calculate declared pairs when
source is all that is available. With rendered access, measure computed colors,
opacity, backgrounds, images and both themes. Check color meaning with a
non-color cue and record every unavailable condition as `Not verified`.

## Useful sources

- [WCAG 2.2 contrast minimum](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html)
- [WCAG 2.2 use of color](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html)
- [WCAG 2.2 non-text contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html)
