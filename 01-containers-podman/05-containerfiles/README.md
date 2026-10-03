# Building images with Containerfiles

> Phase 01 · Containers with Podman · ⏱️ 2 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Containerfile instructions: FROM, RUN, COPY, WORKDIR, ENV, EXPOSE, USER, CMD, ENTRYPOINT
- CMD vs ENTRYPOINT and how arguments combine
- Layer caching — order instructions to rebuild fast
- `.containerignore` to keep junk and secrets out
- Multi-stage builds for small images
- Run as non-root and make files group-0 writable (OpenShift-friendly images)
- `podman build -t`, then run and push your own image

## 🧩 Key ideas

- **Containerfile** — Same format as a Dockerfile. Each instruction creates a layer or sets metadata.
- **Cache** — If a step and everything before it is unchanged, Podman reuses the cached layer. Copy dependency lists before source code.
- **Multi-stage** — Build in a fat image, copy only the result into a slim runtime image.
- **Arbitrary UID** — OpenShift runs containers as a random UID in group 0 by default. Images must not assume root or a fixed UID.

## 🔀 OpenShift vs plain Kubernetes

Images that run fine on Docker often fail on OpenShift because they expect to run as root. Building with `USER 1001` and `chgrp -R 0 && chmod -R g=u` prepares you for SCCs (Phase 6).

## 🍔 Zomato app tie-in

Write a Containerfile for the order service (small Python/Flask or Node app), build it, run it, push it to quay.io under your account.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [Containerfile reference (containers/common)](https://github.com/containers/common/blob/main/docs/Containerfile.5.md)
- [Podman build](https://docs.podman.io/en/latest/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
