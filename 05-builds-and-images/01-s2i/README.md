# Source-to-Image (S2I)

> Phase 05 · Builds and images · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- What S2I does: source + builder image → runnable image
- `oc new-app <git-url>` and what it creates
- Builder images (Python, Node.js, Java)
- Reading build logs (`oc logs -f bc/...`)

## 🧩 Key ideas

- **S2I** — Hand OpenShift your Git repo; it picks a language builder, assembles your app into an image, and deploys it.

## 🔀 OpenShift vs plain Kubernetes

S2I is an OpenShift feature, not plain Kubernetes.

## 🍔 Zomato app tie-in

Build the frontend straight from a GitHub repo with S2I.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

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
