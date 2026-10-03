# Challenge — Images and registries

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - You deploy `:latest`, it works; a week later a new node pulls `:latest` and the app breaks. What happened?
  - Why might `podman pull nginx` ask you to pick a registry?
  - Can two different tags point to the same digest? Can one tag point to two digests?
- **L3 — incident ticket (no hints):** "A pull fails with 'unauthorized' for one image but works for another from the same registry" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
