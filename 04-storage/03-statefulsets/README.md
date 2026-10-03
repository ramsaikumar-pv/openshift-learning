# StatefulSets

> Phase 04 · Storage · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Stable pod names (db-0, db-1) and ordered start/stop
- Headless Services for stable per-pod DNS
- `volumeClaimTemplates` — one PVC per replica
- When to use StatefulSet vs Deployment (and when to use an operator instead)

## 🧩 Key ideas

- **StatefulSet** — Like a Deployment, but each pod has an identity and its own storage that follow it across restarts.

## 🔀 OpenShift vs plain Kubernetes

For real databases on OpenShift, an operator (e.g. a PostgreSQL operator from OperatorHub) is usually better than a hand-written StatefulSet (Phase 8).

## 🍔 Zomato app tie-in

Move the orders DB to a StatefulSet.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
