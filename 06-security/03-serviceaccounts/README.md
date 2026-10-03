# ServiceAccounts

> Phase 06 · Security · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- ServiceAccounts are identities for pods
- Default SA per project; `serviceAccountName`
- Projected, short-lived tokens
- Giving an SA RBAC permissions (e.g. to read ConfigMaps)

## 🧩 Key ideas

- **ServiceAccount** — A non-human user that pods run as when talking to the API.

## 🍔 Zomato app tie-in

Order service gets its own SA with only the access it needs.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Service accounts](https://kubernetes.io/docs/concepts/security/service-accounts/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
