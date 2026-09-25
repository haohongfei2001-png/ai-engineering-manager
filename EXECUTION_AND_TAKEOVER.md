# Execution and Takeover

## One-writer invariant

At most one active writer may modify the same repository + branch + overlapping scope.

Readers, reviewers, CI observers, and managers may coexist.

## Writer lease

Track:
- repo;
- branch;
- scope;
- executor/thread;
- lease state;
- last verified write;
- last verified output;
- active terminal/process evidence if available.

Suggested lease states:
ACTIVE, SUSPECT, STALE, RELEASED, BLOCKED.

## Active is not progress

A UI label such as “active”, “responding”, or “generating” is only a sensor.

Verified progress means at least one relevant signal is advancing:
- new agent output;
- repository write;
- branch head change;
- CI transition;
- durable test/process output.

## Stale-active handling

When a thread claims activity but verified progress stops:

1. inspect remote GitHub;
2. inspect CI and durable execution evidence;
3. determine whether a real process is still running;
4. mark the writer SUSPECT if evidence is ambiguous;
5. mark STALE only when there is no credible ongoing write/process;
6. release the old writer lease;
7. start a new executor from remote truth;
8. tell the new executor not to repeat already-landed work.

Time thresholds are policy defaults, not invariants. Long known operations may legitimately exceed them.

## Takeover conditions

Take over when:
- the next engineering action is clear;
- the old executor cannot accept instructions or has stopped progressing;
- there is no credible concurrent writer;
- remote state can be reconstructed;
- takeover does not cross a product/permission boundary.

## Takeover isolation

When practical, recover in an independent snapshot, worktree, or manager branch rather than modifying an old possibly-stale working directory in place.

Preserve:
- old branches;
- uncommitted user work;
- failed evidence;
- superseded candidate history.

Do not clean or discard old state merely to make takeover easier.

## Takeover procedure

1. Record old executor and last verified progress.
2. Re-read remote main/default branch and active work branch.
3. Read project authority and latest checks.
4. Determine exactly what is complete, failed, and unverified.
5. Establish a new writer lease.
6. Create an isolated recovery workspace/branch when practical.
7. Give the new executor a bounded recovery instruction.
8. Verify the first new durable progress before moving on.
9. After replacement is verified, mark or close obsolete PRs as superseded when project policy allows.
10. Send stop/handoff messages to stale executors when the communication channel is available.

## Superseding old work

A replacement branch or pull request may supersede an abandoned candidate only after the replacement path has been verified against current remote truth.

Do not merge an older candidate over a newer validated main merely because the old thread later wakes up.

## Duplicate-work prevention

If remote already contains a correct implementation:
- do not recreate it;
- verify it;
- repair only remaining failures;
- close the task or move to the next legitimate action.

## Canonical writer registration

A writer lease is not only an in-memory manager concept. When a project has a canonical STATUS/receipt system, activation of a new scope must be reflected there in the first coherent batch so a later manager can discover ownership without chat context.

At minimum record the active scope and writer branch/identity plus the start/base SHA. Record a PR pointer when available without creating a standalone CI-churning commit solely for that metadata. Release or block the writer explicitly at closure.

The portfolio registry may mirror this lease for routing, but it never overrides the repository's canonical state or the actual open PR/head.

## CI-aware stale detection

Do not mark a writer healthy merely because its last action was “wait for CI.”

If the asynchronous job has already reached a terminal state and the writer produces no new durable progress for the normal 30–45 minute watchdog window, classify the writer as SUSPECT/STALLED and recover from remote truth. Conversely, a real running build/test/benchmark with observable job progress is evidence and should not be interrupted only because the wall clock threshold elapsed.

Repeated superseded workflow runs or unchanged-head reruns are signs of execution churn, not progress. Takeover/recovery should preserve the latest useful candidate and avoid replaying obsolete certification.

