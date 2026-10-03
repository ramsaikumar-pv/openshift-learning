# Challenge — Volumes and persistence

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - Bind-mount a directory without `:Z` on a SELinux host — what do you see, and where's the evidence?
  - A Postgres image running as UID 26 can't write to your bind mount — why, and what are two fixes?
  - What happens to a named volume when you `podman rm` the container? With `podman rm -v`?
- **L3 — incident ticket (no hints):** "A database container crash-loops with 'could not open file … Permission denied' after moving its data directory" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
