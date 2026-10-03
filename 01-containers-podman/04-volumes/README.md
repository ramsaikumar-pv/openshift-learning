# Volumes and persistence

> Phase 01 · Containers with Podman · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Container filesystems are ephemeral
- Bind mounts vs named volumes
- SELinux relabelling with `:Z` and `:z`
- Rootless UID mapping and 'Permission denied' on mounts
- `podman unshare` to see files as the container sees them
- `podman volume create/ls/inspect/rm`

## 🧩 Key ideas

- **Bind mount** — A host directory appears inside the container. You manage the path.
- **Named volume** — Podman-managed storage. You refer to it by name; Podman decides where it lives.
- **`:Z` vs `:z`** — `:Z` = private label (only this container); `:z` = shared label (several containers). Without it SELinux blocks access.
- **UID mapping** — UID 0 inside a rootless container is your user outside; other UIDs map into your subuid range.

## 🔀 OpenShift vs plain Kubernetes

OpenShift replaces this with PersistentVolumes and PersistentVolumeClaims (Phase 4) — the same idea, managed by the cluster and backed by storage like vSphere datastores.

## 🍔 Zomato app tie-in

Run PostgreSQL for the orders DB, insert an order, delete the container, start a new one on the same volume — the order survives.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [Podman docs](https://docs.podman.io/en/latest/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
