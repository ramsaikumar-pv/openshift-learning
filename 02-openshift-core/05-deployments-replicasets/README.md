# Deployments and ReplicaSets

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Deployment → ReplicaSet → Pods ownership chain
- Write a Deployment manifest (replicas, selector, template)
- Self-healing: delete a pod and watch it come back
- `ownerReferences` — who owns what
- DeploymentConfig is deprecated — use Deployment

## 🧩 Key ideas

- **ReplicaSet** — Keeps N identical pods matching a selector alive.
- **Deployment** — Manages ReplicaSets so you can roll out new versions and roll back.
- **Template** — The pod blueprint inside the Deployment. Changing it triggers a rollout.

## 🔀 OpenShift vs plain Kubernetes

OpenShift's older `DeploymentConfig` (with triggers/hooks) is deprecated since OCP 4.14. Use standard Deployments; image triggers are done with an annotation.

## 🍔 Zomato app tie-in

Turn the order-service pod into a Deployment with 2 replicas.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
