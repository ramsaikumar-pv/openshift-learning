# Challenge — Ports and container networking

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - What happens if two containers try to publish the same host port?
  - `-p 80:8080` as a rootless user — what error and why?
  - The app logs 'listening on 8080' but curl gets 'connection reset' — what do you check first?
- **L3 — incident ticket (no hints):** "curl to the published port hangs/resets though the container is 'Up'" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
