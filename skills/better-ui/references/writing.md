# Interface writing

Product copy is part of the interaction. It names actions, sets expectations,
explains errors and gives the user a way forward. Review it in the product's
existing terminology and voice rather than imposing a generic personality.

## Terminology and voice

Read nearby copy before changing a phrase. Preserve deliberate brand voice
unless it creates ambiguity, inconsistency, translation risk or an unsuitable
tone for the stakes.

Use one term for one concept throughout a flow. Tone may change with risk:
calm and plain for errors, explicit for destructive or security-sensitive
actions and lighter only where a mistake has low cost.

## Labels and actions

A label should identify the object or action without requiring surrounding
context. Action labels should make the consequence clear. Consequential
confirmation actions should repeat what will happen rather than offer an
ambiguous "Yes" or "OK".

Links should describe their destination or purpose out of context. Do not use
"click here" or duplicate vague labels when several links appear together.

## Errors and recovery

A useful error answers three questions:

1. What failed?
2. What does the user need to know?
3. What can they do next?

Place field-specific guidance beside the field and preserve entered data when
possible. Do not blame the user, expose implementation detail that does not
help recovery or promise a result the system cannot guarantee.

The best recurring error may be an interaction problem, not a wording problem.
If the same error repeats, recommend removing the cause or making the safe path
easier.

## Empty, loading and success states

An empty state should orient the user, explain why the region is empty when
useful and provide the next relevant action. Search and filter empties should
name the active constraint and offer a way to remove or change it.

Loading copy should describe a meaningful wait only when the operation needs
explanation. Success feedback should confirm the result and any next step
without competing with higher-priority work.

## Controls and settings

A toggle label should describe the enabled behavior, not force a double
negative. Button text should not change between steps unless the action changes.
Use complete localized messages for variables and pluralization rather than
assembling fragments around a number.

Placeholders demonstrate format; they do not replace visible labels. Avoid
encoding essential instructions only in placeholder text.

## Localization

Assume translated strings can change length, word order, grammatical gender,
plural form, punctuation and direction. Keep terminology in a translation
catalogue where the product uses one. Avoid idioms, jokes and device-specific
verbs when they create ambiguity or translation risk.

Do not treat English sentence structure as a universal layout contract.

## Verification

Source inspection is often sufficient for copy. Check action labels against the
behavior they invoke, errors against the recovery path, terminology against
neighboring copy and localized message construction against the product's
localization model. Use rendered inspection when wrapping, clipping or state
placement affects meaning.
