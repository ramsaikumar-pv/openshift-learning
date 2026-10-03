# vSphere CSI

> Phase 04 · Storage · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- CSI — the plug-in standard for storage drivers
- vSphere CSI driver: Cloud Native Storage (CNS), datastores, storage policies
- How a PVC becomes a VMDK attached to a node VM
- Day-2: expansion, snapshots, topology/zones (version-dependent)

## 🧩 Key ideas

- **CSI** — Container Storage Interface — vendors write a driver once, every Kubernetes can use it.

## 🔀 OpenShift vs plain Kubernetes

On OpenShift-on-vSphere the vSphere CSI driver is installed and managed by an operator.

## 🍔 Zomato app tie-in

Map Zomato's DB PVC to what you'd see in vCenter at work.

## 🧪 Lab environment

- 🏢 vSphere — your work environment (read-only exploration unless you have a lab)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Storage → vSphere CSI](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
