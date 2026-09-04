# Portable Skills

A public collection of reusable, harness-agnostic skills for software work.
Each skill is self-contained, portable between agent runtimes and free of
runtime dependencies on a particular host, framework or vendor.

## Installation

This repository uses the open Agent Skills layout: each skill is a directory
with a `SKILL.md` entry point and optional supporting files such as
`references/`. The commands below install `better-ui`; replace its path with
another directory under `skills/` when the repository grows.

### Hermes: install one skill

Hermes can install a skill from the public Skills Hub index:

```bash
hermes skills install skills-sh/pawelzny/skills/skills/better-ui
```

You can also install it directly from GitHub through the raw `SKILL.md` URL:

```bash
hermes skills install \
  https://raw.githubusercontent.com/pawelzny/skills/main/skills/better-ui/SKILL.md \
  --yes
```

The raw URL fetches `SKILL.md` and its referenced support files. Use a Git tag
or commit SHA instead of `main` when you need a reproducible version.

### Hermes: add this repository as a tap

A tap registers the repository as a reusable source. It does not install every
skill automatically; install the skills you want from it:

```bash
hermes skills tap add pawelzny/skills
hermes skills install pawelzny/skills/better-ui
```

Check for upstream changes and update an installed skill with:

```bash
hermes skills check better-ui
hermes skills update better-ui
```

### Pi: install the repository

Pi can install this skills-only Git repository as a package. It discovers the
skills under `skills/` without requiring a package manifest:

```bash
pi install https://github.com/pawelzny/skills
```

To load only one skill from a local checkout instead:

```bash
git clone https://github.com/pawelzny/skills.git ~/portable-skills
pi --skill ~/portable-skills/skills/better-ui
```

### Codex: install a personal or project skill

Clone the repository and copy the skill into Codex's personal skill directory:

```bash
git clone https://github.com/pawelzny/skills.git ~/portable-skills
mkdir -p ~/.codex/skills
cp -R ~/portable-skills/skills/better-ui ~/.codex/skills/
```

For a project-local installation, run this from the project root instead:

```bash
mkdir -p .codex/skills
cp -R ~/portable-skills/skills/better-ui .codex/skills/
```

To install the whole collection, copy the contents of the repository's
`skills/` directory:

```bash
cp -R ~/portable-skills/skills/. ~/.codex/skills/
```

### Claude: install a personal or project skill

Clone the repository and copy the skill into Claude's personal skill directory:

```bash
git clone https://github.com/pawelzny/skills.git ~/portable-skills
mkdir -p ~/.claude/skills
cp -R ~/portable-skills/skills/better-ui ~/.claude/skills/
```

For a project-local installation, run this from the project root instead:

```bash
mkdir -p .claude/skills
cp -R ~/portable-skills/skills/better-ui .claude/skills/
```

To install the whole collection, copy the contents of the repository's
`skills/` directory:

```bash
cp -R ~/portable-skills/skills/. ~/.claude/skills/
```

### Versioning

The `version` field in each `SKILL.md` describes the skill release. Git tags
or commit SHAs provide the actual version pin. Use `main` for the latest
contents, or check out a tag or commit in a local clone before copying the
skill into a harness-specific directory.

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
