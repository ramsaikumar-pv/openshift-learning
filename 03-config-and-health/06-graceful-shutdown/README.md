# Graceful shutdown

> Phase 03 · Config and health · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Pod termination sequence: SIGTERM → grace period → SIGKILL
- `terminationGracePeriodSeconds` and `preStop` hooks
- The race between endpoint removal and process exit
- Why exec-form CMD and a proper PID 1 matter

## 🧩 Key ideas

- **SIGTERM** — Polite 'please finish and exit'. The app should stop taking new work and finish in-flight requests.
- **preStop** — Runs before SIGTERM — often a short sleep so routers stop sending traffic first.

## 🍔 Zomato app tie-in

Don't lose an order mid-payment during a rollout.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Pod lifecycle — termination](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
