# Troubleshooting workflows

> Phase 10 · Observability · ⏱️ ongoing · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- A repeatable method: get → describe → events → logs → exec/debug
- `oc debug` (pods and nodes)
- `oc adm must-gather` and `inspect`
- Common states decoded: Pending, ImagePullBackOff, CrashLoopBackOff, OOMKilled, CreateContainerConfigError

## 🧩 Key ideas

- **Method over memory** — Same steps every time, outside-in. The incident tickets in this course drill exactly this.

## 🍔 Zomato app tie-in

Boss levels: multi-fault incidents on the Zomato app.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Support / troubleshooting](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
