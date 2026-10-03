# OLM and OperatorHub

> Phase 08 · Operators · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- OperatorHub and CatalogSources
- Subscription, InstallPlan, ClusterServiceVersion (CSV), OperatorGroup
- Channels and automatic vs manual approval
- Install, upgrade and remove an operator
- OLM v1 (ClusterExtension) — newer, version-dependent

## 🧩 Key ideas

- **Subscription** — 'Keep me on channel X of operator Y' — OLM installs and upgrades accordingly.

## 🍔 Zomato app tie-in

Install a PostgreSQL operator and let it run the orders DB.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Operators](https://docs.redhat.com/en/documentation/openshift_container_platform/)
- [Operator Lifecycle Manager](https://olm.operatorframework.io/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
