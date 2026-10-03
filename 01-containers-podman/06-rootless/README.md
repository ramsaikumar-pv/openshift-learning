# Rootless containers

> Phase 01 · Containers with Podman · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- User namespaces: root in the container ≠ root on the host
- How subuid/subgid ranges are used
- Where rootless storage lives (`~/.local/share/containers`)
- Limits of rootless: low ports, some networking, some mounts
- `podman info` to inspect rootless setup

## 🧩 Key ideas

- **User namespace** — A mapping table: container UID 0 → your UID; container UID 1–65536 → a range from /etc/subuid.
- **Why it matters** — If an attacker escapes a rootless container, they land as an unprivileged user, not root.

## 🔀 OpenShift vs plain Kubernetes

OpenShift's default `restricted-v2` SCC enforces the same philosophy cluster-wide: non-root, no privilege escalation, dropped capabilities.

## 🍔 Zomato app tie-in

Run the payment service rootless and prove from the host side (`ps -o user`) which UID it really runs as.

## 🧪 Lab environment

- 📦 Podman on WSL

## 📚 Official docs

- [Podman rootless tutorial](https://github.com/containers/podman/blob/main/docs/tutorials/rootless_tutorial.md)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
