# ConfigMaps

> Phase 03 · Config and health · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Create ConfigMaps from literals, files and YAML
- Consume as env vars (`env`, `envFrom`) and as mounted files
- What updates live (mounted files) vs needs a restart (env vars)
- `oc set env`, `oc rollout restart`

## 🧩 Key ideas

- **ConfigMap** — Non-secret configuration kept outside the image so one image runs in dev and prod.
- **Projection delay** — Mounted ConfigMap files update after a short delay; env vars never change in a running container.

## 🍔 Zomato app tie-in

Move the order service's DB host and 'max items per order' into a ConfigMap.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
