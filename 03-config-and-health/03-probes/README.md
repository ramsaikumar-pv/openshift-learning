# Health probes

> Phase 03 · Config and health · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Liveness (restart if dead), readiness (remove from Service if not ready), startup (protect slow starters)
- Probe types: httpGet, tcpSocket, exec, grpc
- Tuning: initialDelaySeconds, periodSeconds, timeoutSeconds, failureThreshold
- Reading probe failures in Events

## 🧩 Key ideas

- **Readiness** — Failing = no traffic, no restart. Use it for 'can I serve right now?'
- **Liveness** — Failing = container killed and restarted. Use it only for 'am I stuck beyond recovery?'
- **Startup** — Disables the other probes until it passes once.

## 🍔 Zomato app tie-in

Add `/healthz` and `/ready` endpoints to the order service; readiness checks the DB connection.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Configure probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
