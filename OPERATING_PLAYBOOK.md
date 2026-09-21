# Operating Playbook

## Continuous loop

Run this loop continuously:

Observe → Understand → Prioritize → Act → Verify → Re-prioritize.

## Observe

For every managed project, inspect:
- remote main/default branch and relevant working branch;
- canonical status or project authority docs;
- current developer thread output;
- latest commits and pull requests;
- exact-head CI or required checks;
- deployed / browser / real-product evidence when relevant;
- active writer identity;
- known blockers;
- last verified progress time.

Do not trust stale snapshots when fresh remote evidence is available.

## Understand

Separate facts from claims.

Ask:
- What has actually changed?
- What remains unverified?
- Is the current blocker technical, environmental, authority-related, or product-level?
- Is the developer agent still making verifiable progress?
- Is a proposed large change actually necessary?

## Prioritize

Prefer work that:
1. is closest to real closure;
2. removes a blocker for other work;
3. fixes a specific failing gate;
4. has high confidence and reversible scope;
5. increases information value without consuming protected evaluation resources.

Do not spread attention evenly for its own sake.

## Act

Give concrete instructions tied to current evidence.

Good:
“Re-read the latest remote head and failed job. Reproduce the MEMORY_STALE case, distinguish deterministic regression from timing failure, make the smallest evidence-supported fix, run targeted and full certification, then verify remote.”

Weak:
“Continue.”

The manager may still use a short “continue” when the next action is already unambiguous and the executor is actively following the correct plan.

## Verify

Before accepting completion, check:
- expected commit exists;
- intended branch was updated;
- no unrelated scope was changed;
- required tests actually ran;
- CI status corresponds to the exact relevant head;
- real-product behavior matches the claim when required;
- canonical status/evidence reflects reality;
- later work did not silently invalidate the result.

## Learn

At the end of an engagement:
- keep one-off facts in the handoff;
- promote reusable lessons into policy only when generalizable;
- add a case for subtle decision patterns;
- add an eval for any new material decision rule.
