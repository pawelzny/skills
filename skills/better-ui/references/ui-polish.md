# UI polish

Visual polish should clarify hierarchy and state after interaction, accessibility
and layout are sound. Polish is not a license to add motion, depth or novelty
where the product does not need it.

## Surfaces and depth

Use the project's established surface, border, radius and shadow tokens. Nested
surfaces should have a coherent relationship between padding and radius, but
concentric-radius arithmetic is a heuristic, not a reason to break an existing
component system.

Use borders for structure and state. Use shadows for elevation only when the
layer is actually elevated. Avoid decoration that looks like an interactive
state or reduces contrast against content.

## Optical alignment

Geometric centering is not always optical centering. Icons, asymmetric shapes,
triangles and mixed text/icon controls may need a small adjustment. Verify the
result in context and across direction changes rather than applying a universal
nudge.

## Icons

An icon should clarify an action or state, not replace a necessary label. Keep an
icon set's stroke, size, viewBox and baseline behavior consistent. Use one asset
that can inherit semantic color where the system supports it. Mark decorative
icons as decorative and mirror directional icons in RTL where their meaning is
directional.

Do not add an icon merely to fill an empty area. An unfamiliar icon needs nearby
text, a tooltip or another accessible name according to its risk.

## Motion

Use motion when it explains continuity, hierarchy, feedback or spatial change.
Keep frequent interactions quick and interruptible. Use transitions for state
changes and staged animations only when the sequence communicates something.

A duration, easing, scale or blur value is a recipe to evaluate in context, not a
universal law. Reuse the product's motion language. Every meaningful state must
remain understandable when motion is reduced, skipped or interrupted.

## Performance

Avoid animating layout when transform or opacity can communicate the same
change. Name the properties that transition. Treat `will-change` as a measured
optimization, not a default decoration. Check memory, paint cost, layout shift
and input latency when polish is applied to repeated or large surfaces.

Do not claim a performance improvement from a compositing hint without a
measurement on the target environment.

## Verification

Inspect all defined states, including focus, active, loading, empty, error and
disabled where they exist. At runtime, check interaction feedback, interruption,
reduced motion, stacking order, contrast and hit areas. When animation timing
matters, use a repeatable inspection method and state its result. Leave browser,
device and performance conditions not tested as `Not verified`.
