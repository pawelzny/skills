# Typography

Typography controls hierarchy, reading speed, scanning, data stability and the
survival of real content. Review rendered text where wrapping or font metrics
matter, and keep typography decisions tied to the product's content roles.

## Type system

Identify the active families, available weights and styles, loading strategy,
fallbacks and semantic roles. Prefer a small deliberate scale over scattered
sizes. Name roles by use when that helps the team preserve intent, but do not
rename a stable project system merely to match a convention.

Choose semantics before visual size. Heading levels, labels, body copy, data,
metadata and controls may need different treatments even when they share a
family.

## Weight, line height and measure

Use real font faces where the design depends on them. Synthetic weight or style
can change density and legibility; disabling synthesis globally can remove useful
emphasis from a fallback. Check the full font stack before changing either.

Headings usually need tighter line height than body copy. Multi-line text needs
space to breathe. Set a readable measure for long-form text, but allow dense
operational layouts to justify a different value when the task and content
support it.

Rules such as 16px body text, 1.5 line height or 60–75 characters per line are
starting points, not universal acceptance criteria.

## Wrapping and truncation

Choose wrapping behavior by content role:

- headings may use balancing where supported;
- descriptions should avoid avoidable orphan lines where the browser supports
  the chosen behavior;
- identifiers, URLs and long words need a deliberate overflow strategy;
- badges and compact labels may stay on one line only when the full value
  remains reachable;
- truncation must preserve access to the complete value when it carries meaning.

Verify browser support and fallback behavior for newer text properties. A CSS
declaration is not proof that the rendered result is consistent.

## Data and mixed direction

Use tabular numerals for changing values that must align, such as tables, timers
or counters. Set language and direction metadata. Isolate mixed-direction values
such as user names, identifiers and numbers when they appear inside another
script or sentence.

Keep source text natural and use CSS for presentation. Treat non-breaking spaces,
soft hyphens and punctuation as localization-sensitive content decisions.

## Mobile and zoom

Check input text size against the target browser behavior rather than applying a
single platform folklore rule. Preserve zoom and text resizing. Avoid fixed
heights on text containers and verify that increased text does not hide actions.

## Decorative text treatment

Use underlines, capitalization, tracking and smoothing only when they preserve
meaning and legibility. Non-standard font-smoothing properties can change
perceived weight and contrast; they are not a universal readability fix.

## Verification

Inspect actual font loading, computed size and weight, line height, measure,
wrapping, truncation and direction metadata. Render representative content at
supported widths, zoom levels and locales. Report missing font files, fallback
behavior and unsupported declarations as evidence or `Not verified`, not as
assumed browser behavior.
