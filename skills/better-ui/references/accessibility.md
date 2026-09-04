# Accessibility

Accessibility review asks whether people can perceive, operate, understand and
recover through the interface. Use platform semantics first, verify behavior
where possible and distinguish formal requirements from stronger product goals.

## Native semantics first

Use the native element that already carries the required behavior:

- `button` for an action;
- `a` with a real destination for navigation;
- `input`, `select` and `textarea` for form controls;
- headings, lists, tables and landmarks for document structure.

A custom element must reproduce keyboard, focus, naming, state and input
behavior before it is considered equivalent. ARIA supplements semantics; it
does not repair an incorrect interaction model.

## Keyboard and focus

Walk every task without a pointer:

- every interactive control is reachable;
- focus order follows the task;
- focus is visible against every surface it crosses;
- dialogs move focus into the active region and restore it on close;
- Escape, arrows, Enter and Space follow the widget's established pattern;
- no positive `tabindex` is used to force order;
- pointer-only interactions have a keyboard path.

A focus ring is a functional signal, not decoration. Preserve it in forced-colors
or equivalent high-contrast modes.

## Names, roles and states

Every control needs an accessible name that includes its visible label when one
exists. Icon-only controls need a meaningful name. Decorative media and icons
must not become noise in the accessibility tree.

Expose state in more than color or motion: selected, expanded, pressed, checked,
disabled, busy, invalid and current location must be understandable to the
relevant user agent and assistive technology.

## Forms and errors

Each field has a persistent label, an appropriate type and input mode, and a
useful autocomplete purpose where the field collects recognized personal data.
Never use a placeholder as the only label or block paste without a compelling,
explicit security reason.

Validate at a point that preserves user progress. An error should identify the
field, explain the problem in plain language and state a recovery action. Connect
field-specific help and errors programmatically. Announce untied dynamic
updates with the least disruptive suitable status mechanism.

## Motion and dynamic content

Respect the user's reduced-motion preference. Remove or simplify non-essential
movement, parallax and autoplay rather than merely making them faster. A state
change must remain understandable when animation is skipped or interrupted.

Time-sensitive or auto-updating content needs pause, stop, dismiss or recovery
controls appropriate to its risk. Do not make an error toast disappear before a
user can act on it.

## Zoom, reflow and target size

Test supported text resizing, zoom and narrow widths. Text containers should
expand or wrap rather than clip. Do not disable browser zoom.

WCAG 2.2 Success Criterion 2.5.8 defines a 24 by 24 CSS-pixel minimum target
size at Level AA with exceptions. Products may choose a stronger target such as
44 by 44 CSS pixels, especially for touch. State which baseline applies instead
of presenting a product preference as the standard.

Avoid overlapping invisible hit areas. A larger target is not accessible if it
steals input from a neighboring control.

## Contrast and color meaning

The color domain measures rendered pairs; accessibility determines which
requirement applies. Do not rely on color alone for status, selection, errors or
progress. Include text, shape, position, pattern or another redundant cue.

For formal claims, use the applicable WCAG success criterion and its exceptions.
See [colors.md](colors.md) for measurement ownership.

## Verification

A source review can inspect semantics, labels, focus styles, keyboard handlers,
state attributes, reduced-motion guards and form associations. A rendered review
should also walk the task with keyboard input, inspect the accessibility tree
where available, test target widths and zoom, and check representative assistive
technology behavior.

Automated audits find useful subsets of failures. They do not prove task
completion, correct announcements, understandable recovery or a usable focus
order. Report the exact checks performed and leave the rest `Not verified`.

## Useful sources

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WCAG 2.2 target size](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html)
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
