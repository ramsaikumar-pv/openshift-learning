# PersistentVolumes and Claims

> Phase 04 · Storage · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- PV (the disk) vs PVC (the request for a disk)
- Access modes: RWO, ROX, RWX, RWOP
- Binding, and reclaim policies: Delete vs Retain
- Mount a PVC into a pod and prove data survives pod deletion

## 🧩 Key ideas

- **PVC** — 'I need 5Gi, RWO.' The developer's side.
- **PV** — An actual piece of storage. The admin's (or the provisioner's) side.
- **Access mode** — Block disks (like vSphere VMDKs) are usually RWO — one node at a time.

## 🍔 Zomato app tie-in

Give PostgreSQL a 1Gi PVC; delete the pod; orders survive.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
