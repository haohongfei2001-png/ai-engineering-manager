# Case 006 — Four-project unattended management run

Source snapshot: engineering handoff generated 2026-09-21 07:58 Beijing time.

## Verified outcomes

### Semantic Lab

SCA-03 closed as CALIBRATION_FAIL:
- 80 calibration cases;
- 12 configurations;
- zero winner;
- thresholds were not lowered;
- evaluation was not run.

A later public diagnostic pull request corrected a validation gap by actually invoking centroid/RRF logic across the public topic set and passed its checks. It remained separate from protected private reruns.

### PJSDAS

UU-04 was independently verified complete.

UU-05 had successful CI/browser evidence on its pull request, but review identified a date-only deadline precision regression that still required repair before closure.

### PAIA

A candidate certification failed. Review narrowed one issue to bounded undo test behavior where the final edit targeted one node set while the assertion inspected another. Further certification work was still required.

### HCL

The manager independently reproduced a routing fault in which a JSON repair path lost base_url/api_key information. A minimal candidate passed mock-level validation but had not yet been integrated or fully certified.

## Coordination failure

The common portfolio-level failure was orchestration:
- developer threads stayed active without new final output;
- follow-up sends returned already-responding behavior;
- GitHub stopped advancing;
- browser control was unavailable later in the run.

The manager correctly avoided simultaneous branch takeover when writer ownership could not be established.

## What this case teaches

1. Portfolio managers need executor replacement, not only thread messaging.
2. UI activity is not sufficient evidence of work.
3. A project waiting on one channel should not stop other projects.
4. Negative experimental results can be valid closure.
5. Green checks can coexist with uncovered product regressions.
6. Candidate patches must remain explicitly unverified until integrated and checked.
7. One-writer discipline is necessary for safe autonomous takeover.
