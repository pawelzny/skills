# UX framing

Good interface advice starts with the task, not the pixels. This reference
turns a vague request such as "make this screen better" into a bounded decision
without inventing a product strategy.

## Minimum frame

Capture the smallest useful set:

| Field | Question |
| --- | --- |
| User | Who is performing the task? |
| Task | What are they trying to accomplish? |
| Trigger | What caused them to arrive here? |
| Outcome | What observable result means the task succeeded? |
| Context | Device, environment, frequency, expertise and constraints? |
| Scope | Which screen, component or flow is included? |
| Non-goals | What must not be redesigned in this pass? |
| Risk | What is the cost of confusion, delay or an incorrect action? |
| Evidence | What is known from users, product data, source or runtime? |

Do not fill unknown fields with stereotypes. Mark them as unknown, ask for the
critical ones or proceed with explicit assumptions when the user requests it.

## Critical versus useful questions

Ask only questions that can change the recommendation. A useful order is:

1. Which user and task are we optimizing?
2. What must the user decide or complete?
3. What is currently failing or uncertain?
4. Which platforms, devices, locales and accessibility needs matter?
5. What product, technical or design constraints are fixed?
6. How will we know the change helped?

If several answers are missing, ask them together. If the task is a narrow
implementation review and the missing information cannot change the immediate
finding, state the assumption and continue.

## Task and flow map

For a flow, record:

```text
entry → orientation → input or decision → feedback → recovery → completion
```

For each step, note:

- the user's goal;
- the information needed before acting;
- the available action;
- the system feedback;
- the error or recovery path;
- what persists after navigation or refresh.

A visual improvement that removes orientation, hides recovery or weakens
feedback is not an improvement merely because it looks cleaner.

## Recommendation confidence

Use confidence to separate evidence quality from recommendation strength:

- **High:** reproduced in runtime or directly supported by a product or
  accessibility requirement;
- **Medium:** supported by source and a strong interface heuristic, but not yet
  validated with the relevant user or runtime condition;
- **Low:** plausible interpretation that needs user research, measurement or a
  design experiment.

Confidence does not replace severity. A high-impact issue can have low
confidence and should produce a validation step, not a fabricated certainty.

## Validation choices

Match validation to the claim:

| Claim | Useful validation |
| --- | --- |
| A control cannot be reached | Keyboard and assistive-technology walkthrough |
| Content clips at a width | Render at the supported width and zoom |
| A label is ambiguous | Task walkthrough with representative users |
| A flow is too slow | Instrumented task timing with a defined sample |
| A visual hierarchy is unclear | Comprehension or first-click test |
| A color pair fails | Computed-color measurement against its actual background |
| A change improves a business metric | Controlled experiment or reliable product data |

Never promise a conversion, retention or productivity improvement from a visual
heuristic alone.

## Non-goals

This skill can frame UX decisions, but it is not a substitute for:

- interviews or usability sessions with real users;
- domain research;
- analytics instrumentation;
- product pricing or market validation;
- legal accessibility certification;
- a complete information-architecture program.

Name the missing evidence when it matters.
