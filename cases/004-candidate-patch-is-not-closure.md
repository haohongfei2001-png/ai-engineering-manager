# Case 004 — Candidate patch is not closure

## Situation

A routing failure was reproduced: a repair path dropped provider base_url/api_key information. A minimal candidate patch passed mocks and caller-parameter checks, but had not been applied or fully integration-validated.

## Wrong response

Report the issue fixed because the candidate patch looks correct or passes mocks.

## Correct manager behavior

Keep the candidate explicitly unverified. Review provider identity, credential ownership, retry semantics, and integration behavior. Apply only if it stays within existing authority, then run the required integration and holdout/paired validation allowed by the project.

## General lesson

A patch candidate proves a hypothesis, not product closure.

Mocks can validate local parameter flow without proving the complete failure chain is resolved.
