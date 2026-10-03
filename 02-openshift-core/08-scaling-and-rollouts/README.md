# Scaling and rolling updates

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- `oc scale deployment --replicas`
- RollingUpdate strategy: `maxSurge`, `maxUnavailable`
- Recreate strategy and when to use it
- `oc rollout status`, `history`, `undo`, `pause/resume`
- `oc set image` and why the change should end up in Git

## 🧩 Key ideas

- **Rolling update** — Bring up new pods gradually, remove old ones as new ones become Ready.
- **Revision** — Each template change creates a new ReplicaSet; old ones are kept (scaled to 0) for rollback.

## 🔀 OpenShift vs plain Kubernetes

Same as Kubernetes for Deployments.

## 🍔 Zomato app tie-in

Release order-service v2 with zero downtime, then roll back after a 'bad' v3.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Deployments — updating](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
