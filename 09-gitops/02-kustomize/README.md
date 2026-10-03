# Kustomize

> Phase 09 · GitOps · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Base + overlays, no templating
- Patches (strategic merge, JSON 6902), images, namePrefix, configMapGenerator
- `oc apply -k`, `oc kustomize`

## 🧩 Key ideas

- **Overlay** — A small diff on top of a base: 'prod = base + 3 replicas + bigger limits'.

## 🍔 Zomato app tie-in

Base + dev/prod overlays for the Zomato app.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Kustomize](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
