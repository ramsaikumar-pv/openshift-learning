# Challenge — Building images with Containerfiles

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - You change one line of source and the whole `pip install` reruns — why, and how do you fix the order?
  - `ENTRYPOINT ["python"]` + `CMD ["app.py"]` — what runs with `podman run img other.py`?
  - Shell form vs exec form of CMD — which one receives SIGTERM properly?
- **L3 — incident ticket (no hints):** "A freshly built image works with `podman run` but fails with 'permission denied' when run with a random UID" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

_Nothing yet — dated entries get added after each session._
