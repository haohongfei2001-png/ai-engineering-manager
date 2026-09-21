# Case 005 — Writer lease before takeover

## Situation

A manager had enough information to continue work directly, but the previous developer thread appeared active and branch ownership was not clearly released.

## Wrong response

Start a second writer on the same branch and overlapping scope.

## Correct manager behavior

First determine whether the original writer is still making verifiable progress. Do not take over while a credible write/process is active. Once the old executor is stale or released, record takeover and resume from remote head.

## General lesson

High autonomy does not justify concurrent uncontrolled writers.

The manager should be aggressive about progress and conservative about write ownership.
