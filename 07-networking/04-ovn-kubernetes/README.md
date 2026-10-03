# OVN-Kubernetes

> Phase 07 · Networking · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- CNI — what a network plug-in does
- OVN-K basics: Open vSwitch, cluster/service CIDRs, overlay (Geneve)
- EgressIP and egress firewall (concept)
- Node-level troubleshooting with `oc debug node`
- OpenShift SDN is removed in newer releases — OVN-K is the default

## 🧩 Key ideas

- **CNI** — Container Network Interface: gives each pod an interface and IP and wires up routing.

## 🔀 OpenShift vs plain Kubernetes

OVN-Kubernetes is OpenShift's default CNI; OpenShift SDN was removed in 4.17.

## 🍔 Zomato app tie-in

Trace a packet from the frontend pod to the orders pod.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Networking → OVN-Kubernetes](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
