# Logging

> Phase 10 · Observability · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- `oc logs` (and `--previous`) vs aggregated logging
- OpenShift Logging: collector (Vector) and LokiStack (version-dependent)
- Querying logs across pods

## 🧩 Key ideas

- **Aggregated logging** — Collects logs from every node so they survive pod deletion and can be searched.

## 🍔 Zomato app tie-in

Find every failed payment across all pods in the last hour.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Observability → Logging](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
