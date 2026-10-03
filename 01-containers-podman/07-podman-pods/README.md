# Pods in Podman

> Phase 01 · Containers with Podman · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- A pod = containers sharing one network namespace (and optionally more)
- The infra container that holds the pod's namespaces
- Containers in a pod talk over `localhost`
- `podman pod create/ps/stop/rm`
- `podman kube generate` and `podman kube play` — your bridge to Kubernetes YAML

## 🧩 Key ideas

- **Pod** — The smallest deployable unit in Kubernetes. Podman borrowed the concept so you can practise locally.
- **Shared network** — All containers in a pod share one IP and port space — two can't both listen on 8080.
- **kube play** — Podman can run a (subset of) Kubernetes Pod/Deployment YAML locally.

## 🔀 OpenShift vs plain Kubernetes

This is the exact concept OpenShift schedules. The YAML from `podman kube generate` is very close to what you'll `oc apply` in Phase 2.

## 🍔 Zomato app tie-in

Put the order service and its PostgreSQL in one pod; the service reaches the DB at localhost:5432. Generate the YAML and read it line by line.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [podman-kube-play](https://docs.podman.io/en/latest/markdown/podman-kube-play.1.html)
- [Kubernetes Pods](https://kubernetes.io/docs/concepts/workloads/pods/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
