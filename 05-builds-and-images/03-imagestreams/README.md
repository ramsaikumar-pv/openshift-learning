# ImageStreams

> Phase 05 · Builds and images · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- ImageStream and ImageStreamTag — a pointer layer over real images
- `oc import-image`, `oc tag`, scheduled imports
- Image change triggers on Deployments (annotation)
- Promoting dev → prod by retagging

## 🧩 Key ideas

- **ImageStream** — A named collection of tags that point to image digests. Things can react when a tag moves.

## 🔀 OpenShift vs plain Kubernetes

ImageStreams are OpenShift-only.

## 🍔 Zomato app tie-in

Promote order-service from `:dev` to `:prod` with `oc tag` and watch prod roll out.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Images](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
