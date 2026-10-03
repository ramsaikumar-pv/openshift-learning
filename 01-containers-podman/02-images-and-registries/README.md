# Images and registries

> Phase 01 · Containers with Podman · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Image layers and how they're shared/cached
- Fully-qualified image names: registry/namespace/repo:tag
- Tags vs digests (`@sha256:...`) — mutable vs immutable
- Registries: quay.io, registry.redhat.io (login), registry.access.redhat.com, docker.io
- Short-name resolution and `/etc/containers/registries.conf`
- Red Hat Universal Base Images (UBI)
- `podman pull`, `images`, `inspect`, `tag`, `rmi`, `login`, `push`
- `skopeo inspect` — look at a remote image without pulling

## 🧩 Key ideas

- **Layer** — Each build step adds a layer. Layers are content-addressed, so two images sharing a base store it once.
- **Tag** — A movable label (`:latest`, `:1.2`). Someone can push a different image under the same tag.
- **Digest** — The image's content hash. Pinning by digest guarantees the exact bytes.
- **UBI** — Freely redistributable RHEL-based images — the recommended base for images that run on OpenShift.

## 🔀 OpenShift vs plain Kubernetes

OpenShift has its own internal registry and ImageStreams (Phase 5) that track tags/digests for you. Cluster-wide pull secrets give nodes access to registry.redhat.io.

## 🍔 Zomato app tie-in

Find a UBI Python or Node.js image for the order service; inspect its layers, user and default command.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [Podman docs](https://docs.podman.io/en/latest/)
- [Red Hat Ecosystem Catalog (UBI images)](https://catalog.redhat.com/)
- [skopeo](https://github.com/containers/skopeo)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
