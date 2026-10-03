# What is a container

> Phase 01 · Containers with Podman · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Container vs virtual machine (shared kernel vs own kernel)
- Image vs container (template vs running instance)
- OCI standard — why Podman, Docker, CRI-O all run the same images
- Podman vs Docker: daemonless, rootless by default, CLI-compatible
- `podman run`, `podman ps -a`, `podman logs`, `podman exec`, `podman stop`, `podman rm`
- Container lifecycle states: created, running, exited

## 🧩 Key ideas

- **Image** — A read-only, layered filesystem + metadata (default command, env, user).
- **Container** — A process started from an image with a thin writable layer on top. Delete the container = lose that layer.
- **Daemonless** — Docker CLI talks to a root daemon; Podman forks the container directly as your user. No single daemon to crash or to attack.
- **CRI-O** — The container runtime on OpenShift nodes. Different tool, same OCI images you build with Podman.

## 🔀 OpenShift vs plain Kubernetes

OpenShift nodes don't run Podman or Docker for workloads — kubelet drives CRI-O. Podman is your developer/debug tool (and is on RHCOS for troubleshooting).

## 🍔 Zomato app tie-in

Run a plain nginx container and pretend it's the Zomato frontend's first prototype.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [Podman docs](https://docs.podman.io/en/latest/)
- [Open Container Initiative](https://opencontainers.org/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
