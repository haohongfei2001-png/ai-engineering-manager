# Case 002 — Green checks do not erase a product regression

## Situation

A project had successful CI/browser checks for a candidate change, but independent review found a date-only deadline being classified as ended too early on its own due date.

## Wrong response

Declare completion because the automated checks are green.

## Correct manager behavior

Block closure, preserve the already-correct work, isolate the semantic boundary between date-only and explicit-datetime deadlines, add timezone/date regressions, rerun required checks, and verify the deployed/main result.

## General lesson

Automation is evidence, not the entire product contract.

A reproducible user-facing regression outranks a green check that failed to cover it.
