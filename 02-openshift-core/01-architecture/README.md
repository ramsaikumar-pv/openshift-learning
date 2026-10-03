# Architecture

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Control plane: kube-apiserver, etcd, scheduler, controller-manager
- Worker nodes: kubelet, CRI-O, kube-proxy/OVN
- Desired state vs actual state — the reconciliation loop
- What OpenShift adds on top of Kubernetes
- RHCOS and cluster operators (`oc get clusteroperators`)
- Kubernetes version vs OpenShift version (e.g. OCP 4.x ↔ K8s 1.y)

## 🧩 Key ideas

- **API server** — The front door. Every `oc` command, the console and every controller talk only to it.
- **etcd** — The key-value database holding all cluster state. Lose it without backup = lose the cluster (Phase 11).
- **Scheduler** — Picks a node for each new pod based on resources, rules and affinity.
- **Controllers** — Loops that watch desired state and act until actual state matches. Deployments, ReplicaSets, etc. all work this way.
- **Cluster operators** — OpenShift manages its own components (ingress, registry, DNS, console…) with operators.

## 🔀 OpenShift vs plain Kubernetes

Kubernetes is the engine; OpenShift is a full distribution: RHCOS, integrated registry, Routes, built-in OAuth, SCCs, monitoring, the console, OLM, and an operator-managed upgrade path.

## 🍔 Zomato app tie-in

Draw the Zomato app on top of the cluster: which component decides where the order-service pod runs, and who restarts it if it dies?

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Kubernetes architecture](https://kubernetes.io/docs/concepts/architecture/)
- [OpenShift docs → Architecture](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
