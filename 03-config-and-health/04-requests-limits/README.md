# Requests, limits and quotas

> Phase 03 · Config and health · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Requests (scheduling guarantee) vs limits (hard cap)
- CPU over limit = throttled; memory over limit = OOMKilled
- QoS classes: Guaranteed, Burstable, BestEffort
- LimitRange and ResourceQuota on a project
- `oc adm top pods` / metrics

## 🧩 Key ideas

- **Request** — What the scheduler reserves on a node for the pod.
- **Limit** — The ceiling enforced by cgroups (Phase 0 pays off here).
- **Quota** — A budget for a whole project — the Sandbox has one.

## 🍔 Zomato app tie-in

Size the order service and the DB; see what the Sandbox quota allows.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
