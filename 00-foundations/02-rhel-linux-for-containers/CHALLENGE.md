# Challenge — RHEL Linux for containers

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - What does `podman run -v ./data:/data` do differently with and without `:Z` on SELinux?
  - If SELinux is set to permissive to 'fix' an error, what did you actually just turn off?
  - Why does `ss -tlnp` show 127.0.0.1:8080 vs 0.0.0.0:8080 and why does it matter for containers?
- **L3 — incident ticket (no hints):** "A service won't start after a config change and the error says 'Permission denied' even as root" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
