# Helm

> Phase 09 · GitOps · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Charts, values, templates, releases
- `helm install/upgrade/rollback/uninstall`, `helm template`
- Writing a small chart for the order service
- Helm charts in the OpenShift console

## 🧩 Key ideas

- **Chart** — A templated package of manifests with configurable values.

## 🍔 Zomato app tie-in

Chart the Zomato app with values for dev and prod.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Helm docs](https://helm.sh/docs/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
