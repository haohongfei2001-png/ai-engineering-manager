# Case 007 — Successful four-project takeover and closure

Source: engineering manager closure report completed 2026-09-21 11:08 Beijing time.

## Starting condition

Four projects had unfinished closure work after an earlier unattended run. Old developer tasks remained nominally active but showed no new output, repository commits, active CI, or relevant execution processes.

The manager did not treat the old “active” state as real progress.

## Takeover method

The manager:
- re-read each project’s remote main, pull requests, checks, canonical state, and latest task output;
- used independent directories and manager branches for takeover;
- did not rewrite old branches or discard uncommitted files;
- preserved failed evidence and superseded candidates;
- kept one effective writer per affected scope;
- later sent stop/handoff messages to the old tasks after confirming they were idle.

This converted the stale-worker policy from a theoretical rule into a verified recovery pattern.

## PJSDAS outcome

The manager inherited a nearly-complete usability round but found a date-only deadline precision regression.

It:
- repaired date-only semantics without weakening datetime behavior;
- added timezone and yesterday/today/tomorrow regressions;
- corrected an expired fixed test clock rather than weakening assertions;
- superseded the old pull request with a verified replacement;
- verified CI, browser checks, deployment, production self-test, release behavior, and canonical closure.

The round closed COMPLETE. The next round remained READY and was not automatically started.

## Semantic Lab outcome

The manager merged the already-reviewed public diagnostic work and verified exact-main CI.

It preserved the prior CALIBRATION_FAIL result:
- no private calibration/evaluation reread;
- no threshold change;
- no private lockbox consumption;
- no unauthorized architecture change.

The next protected stage remained BLOCKED.

## PAIA outcome

The manager repaired certification failures without changing production runtime logic.

It:
- fixed bounded undo test targeting while preserving global undo semantics and source/digest invariants;
- aligned an old large-window assertion with a later frozen window contract and added duplicate checks;
- corrected an expired fixture clock while preserving production freshness rules;
- preserved all prior failure history;
- reran the required browser and full-suite certification to an exact runtime/test head;
- recorded completion in a later documentation-only head without pretending that docs head was the runtime-certified SHA.

The current round closed COMPLETE. The next round remained READY / NOT_STARTED.

## HCL outcome

The manager rejected an insufficient forwarding-only candidate because it did not safely preserve repair-model/provider identity.

It implemented a fuller same-provider routing repair that:
- preserved base_url/api_key forwarding;
- explicitly bound the original provider/model;
- rejected incompatible cross-provider repair before sending;
- preserved frozen retry/credential behavior;
- passed targeted and integration validation.

It did not rerun or relabel the previously incomplete holdout as a fresh success.

## Additional operational lesson: freshness

During PAIA verification, an observation tool repeatedly returned stale state for the same URL. The manager used a fresh query path rather than mistaking cached data for lack of progress.

This establishes a second-order rule:
observability itself must sometimes be verified.

## Closure behavior

All four intended closure targets were completed. No new next-round scope was started. No new credentials, paid services, force pushes, or owner permissions were required.

## General lessons

1. A stale-worker takeover can safely complete work when remote truth is reconstructable.
2. Independent takeover workspaces reduce the risk of damaging old local state.
3. Superseded pull requests should be replaced only after the new path is verified.
4. Exact-head certification should identify the runtime/test SHA; later closure-doc commits should not create artificial self-certification loops.
5. Cached observability can be wrong; verify freshness before changing project state.
6. Closing the current scope does not authorize the next scope.
7. A manager can autonomously finish substantial engineering work without expanding product, credential, privacy, or evaluation boundaries.
