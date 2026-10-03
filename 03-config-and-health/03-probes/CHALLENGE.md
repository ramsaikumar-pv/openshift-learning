# Challenge — Health probes

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - Liveness probe checks the database — the DB blips for 30s. What happens to every order-service pod?
  - Readiness failing on all pods — what does the Route return?
- **L3 — incident ticket (no hints):** "Pods restart every couple of minutes with no errors in the app log" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
