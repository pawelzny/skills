# Layout

Layout communicates hierarchy, sequence and affordance before the user reads
all of the copy. Review the relationship between content, controls and
containers rather than applying a universal spacing scale.

## Structure and grouping

Group items that share a task or meaning. Use space and alignment first,
backgrounds second and separators only when the first two cannot carry the
relationship. The stronger the relationship, the closer and more consistent
the grouping should be.

A control must be distinguishable from nearby static content through an
established affordance: native styling, a consistent placement zone, an
underline, a border or another project convention. Do not force every link to
look like a filled button.

## Alignment and reading order

Choose shared edges deliberately. Visual order should support the user's task
and match DOM or accessibility order unless a documented exception is verified.
Use logical properties for localizable layouts and reason in leading/trailing
terms rather than assuming left-to-right direction.

A visually clever arrangement that makes scanning, keyboard traversal or RTL
comprehension harder is a regression.

## Progressive disclosure

Hidden content needs a visible cue: a disclosure control, a label, a preview,
a count or an established scroll affordance. A partially visible next item can
hint at continuation, but it must not be the only way to reach critical content.

Disclosure state must be understandable, operable and restorable. Do not hide a
recovery action behind an affordance that is unclear at the moment of failure.

## Responsive behavior

Breakpoints are consequences of content and interaction, not device-name
rituals. Preserve the task and priority order as the container changes. Check:

- the smallest supported width;
- the widest supported width;
- intermediate widths where columns collapse;
- long labels and translated strings;
- keyboard focus while containers reflow;
- sticky or fixed controls against safe areas;
- horizontal scrolling only where the content model justifies it.

Container queries can be useful for reusable components, but they are not a
requirement. Use the project's established responsive mechanism.

## Density and breathing room

Density is a product decision. A dense professional tool and a consumer reading
flow need different amounts of space. Start from the existing density system;
where none exists, use a consistent relationship between intra-group and
inter-group spacing and verify it with real content.

Do not add whitespace merely to make a screenshot feel expensive, and do not
compress a task until targets overlap or hierarchy disappears.

## Content growth

Assume labels can grow because of localization, user content, permissions or
future features. Avoid fixed dimensions on text containers. Let rows wrap or
provide an intentional overflow and recovery path. Test pseudo-localized or
representative long strings instead of budgeting an arbitrary percentage.

## Verification

Inspect source order, logical properties, container rules and fixed dimensions.
At runtime, resize through supported widths, zoom the page, try long content,
check RTL where relevant and follow keyboard focus through reflow. Record every
condition not tested as `Not verified`.
