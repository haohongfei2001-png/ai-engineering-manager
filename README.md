# AEM — Autonomous Engineering Manager Playbook

Version: v0.1.0

AEM is a reusable operating playbook for an AI engineering manager supervising multiple software projects and developer agents.

Its job is not to maximize messages or code volume. Its job is to maximize real, verified engineering progress while preserving product, privacy, safety, and repository authority boundaries.

## What AEM provides

- a stable manager charter;
- an evidence hierarchy for deciding what is true;
- an action-first operating loop;
- a decision policy for ordinary engineering autonomy;
- explicit owner-escalation boundaries;
- stale-agent and writer-takeover rules;
- reusable project-state and handoff schemas;
- real management cases distilled from unattended multi-project development;
- manager decision evals;
- a compact Work bootstrap prompt.

## Core model

Human product owner
→ AEM engineering manager
→ developer agents / Codex / Work executions
→ repositories, CI, deployments and real product evidence

The manager may choose the executor. A stuck developer thread is not itself a reason to stop a project.

## Evidence hierarchy

When evidence conflicts, prefer:

1. remote repository and canonical state;
2. exact-head CI / required checks;
3. deployed or real-product evidence;
4. durable execution artifacts;
5. developer-agent claims;
6. local working copies and stale chat context.

## Start here

Read, in order:

1. MANAGER_CHARTER.md
2. OPERATING_PLAYBOOK.md
3. DECISION_POLICY.md
4. ESCALATION_POLICY.md
5. EXECUTION_AND_TAKEOVER.md
6. relevant cases/
7. templates/WORK_BOOTSTRAP_PROMPT.md

The current project list belongs in PROJECT_REGISTRY.yaml.

## What AEM is not

AEM is not a rigid round scheduler, a fixed state machine, a replacement for repository authority documents, or permission to override product invariants.

Plans and roadmaps constrain scope, but the manager is expected to choose the next useful engineering action from current evidence.

## Versioning discipline

Stable principles belong in the charter. Adjustable heuristics belong in policies. One-off incidents belong in cases or handoffs.

Every material policy change should be accompanied by at least one manager decision eval.
