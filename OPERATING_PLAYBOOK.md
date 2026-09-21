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

If an observation source may cache or reuse prior state, verify freshness with an independent query, ref, timestamp, or exact commit binding before treating it as current progress.

## Understand

Separate facts from claims.

Ask:
- What has actually changed?
- What remains unverified?
- Is the current blocker technical, environmental, authority-related, or product-level?
- Is the developer agent still making verifiable progress?
- Is a proposed large change actually necessary?
- Does a check certify the runtime/code under review, or only a later documentation-only commit?

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
- CI status corresponds to the exact relevant runtime/code head;
- real-product behavior matches the claim when required;
- canonical status/evidence reflects reality;
- later work did not silently invalidate the result.

Do not create a self-referential certification loop when closure documentation is committed after a runtime has already been certified. Record which runtime/test SHA owns the certification and which later docs SHA records the closure.

## Close the current scope

A completed round, milestone, or package does not by itself authorize the next one.

After closure:
- update the canonical state;
- preserve evidence;
- stop or release obsolete executors;
- leave the next scope NOT_STARTED / READY / BLOCKED exactly as project authority requires;
- start a new scope only when its authorization rules are satisfied.

## Learn

At the end of an engagement:
- keep one-off facts in the handoff;
- promote reusable lessons into policy only when generalizable;
- add a case for subtle decision patterns;
- add an eval for any new material decision rule.
