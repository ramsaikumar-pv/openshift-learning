# BuildConfigs

> Phase 05 · Builds and images · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- BuildConfig strategies: Source (S2I), Docker (Containerfile)
- Triggers: ConfigChange, ImageChange, webhooks
- `oc start-build`, `oc cancel-build`, build history
- Builds for OpenShift (Shipwright) as the newer path — version-dependent

## 🧩 Key ideas

- **BuildConfig** — A recipe for building an image; each run is a Build object.

## 🔀 OpenShift vs plain Kubernetes

BuildConfigs are OpenShift-only. Red Hat's 'Builds for OpenShift' (Shipwright-based) is the newer model — check what your version supports.

## 🍔 Zomato app tie-in

Docker-strategy build for the order service using the Containerfile from Phase 1.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Builds](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
