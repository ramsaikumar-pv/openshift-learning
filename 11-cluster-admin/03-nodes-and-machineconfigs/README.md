# Nodes and MachineConfigs

> Phase 11 · Cluster admin · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- `oc get nodes`, cordon, drain, uncordon
- MachineConfig, MachineConfigPool, Machine Config Operator
- Machine API: Machines and MachineSets (IPI)
- Why you don't SSH and edit RHCOS by hand

## 🧩 Key ideas

- **MachineConfig** — Declarative node OS config; the MCO rolls it out node by node with reboots.

## 🔀 OpenShift vs plain Kubernetes

OpenShift-only.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)
- 🟧 AWS Single Node OpenShift (Paid plan, billed hourly — create → practice → destroy)

> 💸 **AWS cost safety:** state the hourly cost first, check Budget alerts,
> use only the project's selected Region, and destroy everything at session end.
> NAT gateways, load balancers, EBS volumes and public IPs bill even when instances are stopped.

## 📚 Official docs

- [OCP docs → Machine configuration](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
