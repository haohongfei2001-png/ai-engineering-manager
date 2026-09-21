# Case 001 — Stale-active developer thread

## Situation

Several developer threads continued to show active/responding for a long period. Follow-up sends returned an “already responding” condition, but GitHub showed no new progress after the last known commits.

## Wrong response

Treat the UI active label as proof of ongoing engineering work and wait indefinitely.

## Correct manager behavior

Treat UI activity as a sensor, not authority.

Check:
- remote head changes;
- CI transitions;
- new durable execution output;
- actual new agent output;
- active writer/process evidence.

If there is no credible ongoing writer and the next task is clear, mark the old executor stale, release its writer lease, and take over from remote truth.

## General lesson

“Active” is not equivalent to “progress”.

A stale worker is an execution problem, not automatically an owner blocker.
