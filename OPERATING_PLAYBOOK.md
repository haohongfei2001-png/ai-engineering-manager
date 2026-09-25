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

## Throughput and CI discipline

### Coherent engineering batch

The default write unit is a coherent engineering batch, not a single edited line or a CI-triggering micro-commit.

Before a remote push:
- finish the related implementation and directly affected tests that can be completed together;
- inspect the complete diff for the current concern;
- prefer one stable candidate push over a sequence of speculative pushes;
- when performing GitHub-only multi-file management edits, prefer one Git Data tree/commit/ref update when available rather than sequential contents-API commits;
- do not push merely to ask CI what an obvious local/static check can answer.

A new remote head is justified by a coherent implementation increment, a correction based on new evidence, or a required integration/closure record. Cosmetic bookkeeping alone must not repeatedly invalidate a certified runtime head.

### Verification depth

Use three evidence depths:

1. **Inner loop** — static checks, unit tests, focused fixtures and directly affected browser tests. Run freely without full historical certification.
2. **Candidate / light integration** — after a coherent batch push, run the smallest cloud gate that protects the changed invariants.
3. **Boundary certification** — full browser/device/platform/performance/reliability suites only at a canonical round/slice/release boundary, or immediately for a high-risk invariant whose delayed failure would invalidate later work.

Do not rerun a failed or successful heavy workflow on an unchanged head unless there is concrete transient CI/environment evidence. Do not keep following superseded runs. A newer head owns the next certification.

Research repositories are an exception only where the frozen protocol requires a fresh-evidence boundary: batching must never merge independent blind evaluations, consumed tests, freeze transitions or adjudication boundaries merely to reduce CI count.

### Writer registration at start

Writer ownership is part of the round start, not post-hoc closure bookkeeping.

The first coherent change of a new active scope must make the repository's canonical status truthful about:
- ACTIVE/IN_PROGRESS state;
- writer branch or equivalent writer identity;
- PR when already known;
- start/base SHA;
- current engineering frontier.

Do not create a standalone runtime-invalidating commit only to add a PR number after the PR is opened. Add that pointer in the next coherent metadata/engineering update. At closure, release the writer explicitly.

### Portfolio routing index

`PROJECT_REGISTRY.yaml` is the portfolio routing index. It is not a replacement for project truth.

Before cross-project scheduling:
- refresh the relevant remote main, open PR/head and canonical project status;
- use the registry to identify priority, expected routing state, canonical status path and likely owner/external gates;
- if registry and repository truth differ, repository truth wins and the registry should be corrected in the next manager-policy batch;
- an ACTIVE/READY project with no blocker and no writer must be surfaced as an attention state, not silently treated as healthy;
- do not start a writer solely because the registry says ACTIVE without checking the repository's current writer ownership.

### Stalled and CI-churn classification

Treat UI activity as non-authoritative. For an active/authorized project, 30–45 minutes with no new commit, PR-head movement, CI transition, merge, receipt/status progress or credible long-running process is a stall signal when the last action was only asynchronous waiting.

Classify CI churn when any of the following recur without new engineering information:
- several micro-pushes repeatedly supersede or cancel prior runs;
- full/heavy certification runs on intermediate heads that are not integration candidates;
- the same unchanged head is rerun without transient-environment evidence;
- an agent sleeps/polls instead of ending the turn and resuming from GitHub truth;
- product code is changed to satisfy an obvious harness defect instead of repairing the harness.

The manager should stop the churn, preserve the latest useful head, and resume with a coherent batch.

