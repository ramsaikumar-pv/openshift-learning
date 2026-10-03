# Challenge — Deployments and ReplicaSets

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - Delete the ReplicaSet directly — what happens?
  - Selector doesn't match the template labels — what does the API say?
  - Create a bare pod with the same labels as a Deployment's pods — what does the ReplicaSet do to it?
- **L3 — incident ticket (no hints):** "A Deployment shows 0/3 ready and no pods exist at all" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
