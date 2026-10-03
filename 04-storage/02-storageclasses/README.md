# StorageClasses and dynamic provisioning

> Phase 04 · Storage · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Dynamic provisioning via a StorageClass
- Default StorageClass
- `volumeBindingMode: WaitForFirstConsumer` vs Immediate
- Volume expansion (`allowVolumeExpansion`)

## 🧩 Key ideas

- **StorageClass** — A storage 'menu item' (like a vSphere storage policy): who provisions, with what parameters.

## 🍔 Zomato app tie-in

Compare the Sandbox's storage classes with CRC's.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Storage classes](https://kubernetes.io/docs/concepts/storage/storage-classes/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
