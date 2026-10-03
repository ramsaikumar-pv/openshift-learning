# Upgrades

> Phase 11 · Cluster admin · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Update channels (stable, fast, candidate, eus)
- Cluster Version Operator and the update graph
- Pre-upgrade checks and watching an upgrade
- EUS-to-EUS upgrades

## 🧩 Key ideas

- **CVO** — Cluster Version Operator — orchestrates upgrading every cluster operator in order.

## 🔀 OpenShift vs plain Kubernetes

OpenShift upgrades the whole platform (OS + Kubernetes + operators) as one unit.

## 🧪 Lab environment

- 🟧 AWS Single Node OpenShift (Paid plan, billed hourly — create → practice → destroy)

> 💸 **AWS cost safety:** state the hourly cost first, check Budget alerts,
> use only the project's selected Region, and destroy everything at session end.
> NAT gateways, load balancers, EBS volumes and public IPs bill even when instances are stopped.

## 📚 Official docs

- [OCP docs → Updating clusters](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
