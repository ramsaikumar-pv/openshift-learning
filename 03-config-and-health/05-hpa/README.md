# Horizontal Pod Autoscaler

> Phase 03 · Config and health · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- HPA scales replicas on CPU/memory (or custom metrics)
- Why HPA needs requests set
- `oc autoscale` and HPA YAML (autoscaling/v2)
- Generate load and watch scaling; scale-down stabilisation

## 🧩 Key ideas

- **HPA** — A controller that changes `replicas` on your Deployment based on metrics.
- **Utilisation** — Measured as a percent of the request, not the limit.

## 🔀 OpenShift vs plain Kubernetes

Custom-metrics autoscaling in OpenShift is commonly done with the Custom Metrics Autoscaler (KEDA-based) operator.

## 🍔 Zomato app tie-in

Lunch rush: autoscale the order service between 2 and 6 replicas.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Horizontal Pod Autoscaling](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
