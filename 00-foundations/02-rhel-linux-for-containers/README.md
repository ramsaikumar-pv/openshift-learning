# RHEL Linux for containers

> Phase 00 · Foundations · ⏱️ 2–3 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Linux namespaces (pid, net, mnt, uts, ipc, user) — what isolates a container
- cgroups v2 — what limits a container's CPU/memory
- SELinux basics: modes, contexts (`ls -Z`, `ps -Z`), `container_t`, and why `:Z` exists
- systemd units and `journalctl` — how services run and log on RHEL/RHCOS
- `dnf` package management on RHEL and UBI images
- `firewalld` zones and services (and why OpenShift nodes manage this for you)
- UIDs, `/etc/subuid` and `/etc/subgid` — the base of rootless containers
- Network troubleshooting toolkit: `ss`, `ip`, `dig`, `curl -v`

## 🧩 Key ideas

- **A container is just a process** — Started with its own set of namespaces (what it can see) and cgroups (how much it can use). No separate kernel.
- **SELinux** — Mandatory access control: even root is denied unless the label policy allows it. Containers run as `container_t` and can only touch files labelled for them.
- **RHCOS** — OpenShift nodes run Red Hat Enterprise Linux CoreOS — immutable, managed by the cluster. You rarely SSH in; you use `oc debug node/<name>`.
- **journald** — systemd's log store. kubelet and CRI-O on every node log here.
- **subuid/subgid** — Ranges of host UIDs a normal user may map into a container, so 'root inside' is an unprivileged UID outside.

## 🔀 OpenShift vs plain Kubernetes

OpenShift nodes are RHCOS, SELinux is always enforcing, and nodes are configured through MachineConfigs (Phase 11) instead of editing files by hand.

## 🍔 Zomato app tie-in

Imagine the payment service is compromised: which of namespaces, cgroups and SELinux each stop it from reading the order DB's files or eating all the node's memory?

## 🧪 Lab environment

- 🐧 Ubuntu on WSL (your laptop)
- 🎩 A RHEL 9/10 machine — free Red Hat Developer subscription VM (Ubuntu WSL has no SELinux/firewalld by default)

## 📚 Official docs

- [RHEL documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/)
- [Red Hat Developer subscription (free RHEL)](https://developers.redhat.com/products/rhel/overview)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
