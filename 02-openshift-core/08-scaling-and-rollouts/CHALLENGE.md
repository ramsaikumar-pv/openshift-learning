# Challenge — Scaling and rolling updates

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - New version's image tag doesn't exist — what happens to the old pods during the rollout?
  - `maxUnavailable: 0` and `maxSurge: 0` together — what does the API say?
  - Scale to 0 — what happens to the Service and the Route?
- **L3 — incident ticket (no hints):** "A rollout is stuck at '1 out of 3 new replicas have been updated'" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
