# Ports and container networking

> Phase 01 · Containers with Podman · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Each container gets its own network namespace
- Publishing ports with `-p hostPort:containerPort`
- Why the app must listen on 0.0.0.0, not 127.0.0.1
- Rootless containers can't bind host ports below 1024 by default
- `podman port`, `curl`, `ss` to verify the path end-to-end

## 🧩 Key ideas

- **Network namespace** — The container has its own interfaces, IPs and port space — port 8080 inside isn't automatically reachable outside.
- **Port publish** — A forwarding rule: traffic to the host's port goes to the container's port.
- **Listen address** — An app bound to 127.0.0.1 only accepts connections from inside its own namespace.

## 🔀 OpenShift vs plain Kubernetes

In OpenShift you don't publish ports on hosts. Services and Routes (Phase 2) give pods stable addresses and external URLs.

## 🍔 Zomato app tie-in

Run the frontend on host port 8080 and the order service on 8081; curl both.

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
