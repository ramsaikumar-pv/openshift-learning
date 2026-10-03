# What is an operator

> Phase 08 · Operators · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Custom Resource Definitions (CRDs) and Custom Resources
- Operator = CRD + controller encoding ops knowledge
- Cluster operators that run OpenShift itself (`oc get co`)
- Reading an operator's CR status

## 🧩 Key ideas

- **Operator** — Software that does what an expert admin would: install, configure, upgrade, back up, heal.

## 🔀 OpenShift vs plain Kubernetes

OpenShift is built from operators; plain Kubernetes doesn't ship OLM.

## 🍔 Zomato app tie-in

Look at how a database operator would manage the orders DB.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Operator pattern](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
