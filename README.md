# Portable Skills

A public collection of reusable, harness-agnostic skills for software work.
Each skill is self-contained, portable between agent runtimes and free of
runtime dependencies on a particular host, framework or vendor.

## Skills

- [`better-ui`](skills/better-ui/SKILL.md): evidence-based UI and UX review,
  recommendations, accessibility checks, visual-system guidance, component
  stress testing, variants and interface explanation.

## Design principles

- **Context before taste.** A product's users, tasks, constraints and local
  design system are evidence. Generic guidance never silently overrides them.
- **Evidence before certainty.** Separate observed facts, derived values,
  inferences and unverified hypotheses.
- **Requirements before heuristics.** Accessibility requirements, product
  constraints and browser behavior are not interchangeable with design taste.
- **Read-only by default.** Review and recommendation do not authorize edits.
  Exploratory artifacts require an explicit request and a reversible scope.
- **Portable by design.** The skill describes capabilities and checks rather
  than assuming a command, tool protocol, browser integration or framework.

## Package layout

Each skill has one entry point and optional reference files:

```text
skills/<skill-name>/
  SKILL.md
  references/
```

`SKILL.md` owns the workflow. Reference files hold domain depth, recipes and
output contracts. They are not independent skills and should not be loaded as
unrelated procedures.

## Using a skill

Load the relevant `SKILL.md` through the host's normal skill mechanism. The
host may provide different capabilities for source inspection, rendered-page
inspection, image analysis, version-control review or file changes. The skill
must use the capabilities that are available and mark unavailable checks as
`Not verified`; it must not invent a substitute result.

## Provenance

`better-ui` is an independent, harness-agnostic adaptation informed by the
public `jakubkrehel/skills` collection and its interface-design material:
<https://github.com/jakubkrehel/skills>.

The source collection is MIT-licensed. This repository is also distributed
under the MIT License. The adaptation removes host-specific commands and
policies, separates requirements from heuristics and leaves product-specific
rules to the project that consumes the skill.
