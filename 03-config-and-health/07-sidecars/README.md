# Multi-container pods and sidecars

> Phase 03 · Config and health · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Init containers: run to completion before the app starts
- Sidecar pattern: helper container alongside the app (logs, proxy)
- Native sidecars (`restartPolicy: Always` in initContainers) — version-dependent
- Sharing data with an `emptyDir` volume

## 🧩 Key ideas

- **Init container** — E.g. wait for the DB, or run migrations, before the app starts.
- **Sidecar** — Lives as long as the app. Native sidecars start before and stop after the main container.

## 🔀 OpenShift vs plain Kubernetes

Native sidecar support depends on the Kubernetes version under your OCP release — check before relying on it.

## 🍔 Zomato app tie-in

Init container waits for Postgres; a sidecar tails the order log.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Init containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/)
- [Sidecar containers](https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
