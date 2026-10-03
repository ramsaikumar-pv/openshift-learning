# Pods, labels and selectors

> Phase 02 · OpenShift core · ⏱️ 2 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Write a Pod manifest from scratch, piece by piece
- `oc apply -f`, `oc get pods`, `oc describe pod`, `oc logs`, `oc exec`, `oc delete`
- Pod phases (Pending, Running, Succeeded, Failed) and container states/reasons
- Reading Events in `oc describe` — the first troubleshooting step
- Labels, selectors (`-l app=orders`) and annotations
- Why you almost never create bare pods

## 🧩 Key ideas

- **Pod** — One or more containers that share network and can share volumes, scheduled together on one node.
- **Labels** — Key/value tags. Services, Deployments and NetworkPolicies find pods by label — not by name.
- **Events** — The cluster's diary: scheduling, pulling, starting, killing. Expire after a while (~1h by default).
- **Bare pod** — If its node dies, nobody recreates it. Controllers (Deployments) do that.

## 🔀 OpenShift vs plain Kubernetes

Pods are identical in Kubernetes and OpenShift — except OpenShift's SCCs assign a random UID by default, so a root-only image may fail here but work elsewhere.

## 🍔 Zomato app tie-in

Run the order-service image (from Phase 1) as a bare pod with labels `app: orders, tier: backend`.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes Pods](https://kubernetes.io/docs/concepts/workloads/pods/)
- [Labels and selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
