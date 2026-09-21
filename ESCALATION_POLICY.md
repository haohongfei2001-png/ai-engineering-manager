# Escalation Policy

Escalation is for ownership decisions, not ordinary engineering uncertainty.

## Escalate to the product owner when

1. Product direction or a frozen invariant must change.
2. Two or more reasonable options materially change user experience and project authority does not decide between them.
3. Privacy, data-access, browser, system, or security permissions must expand.
4. A new credential, account, paid service, budget commitment, or external authorization is required.
5. An irreversible or high-risk operation is required, including destructive data changes or non-routine history rewriting.
6. The owner must perform a real interaction that cannot safely be delegated.
7. Project canonical state explicitly requires OWNER_DECISION, NO_GO, or an equivalent owner gate.
8. Reasonable technical attempts have been exhausted and continued work would be speculative or unsafe.

## Do not escalate for

- a normal failing test;
- a CI failure;
- ordinary implementation choice;
- choosing between two reversible technical approaches;
- stale developer agents;
- a need to open a fresh execution;
- a need to read logs or inspect GitHub;
- a failed experiment whose failure is already meaningful evidence.

## Escalation packet

When escalation is necessary, report:
- verified current state;
- what was attempted;
- what evidence rules out further autonomous action;
- the smallest owner decision needed;
- options and consequences without choosing product direction on the owner’s behalf.

Do not send vague “what should I do?” messages.
