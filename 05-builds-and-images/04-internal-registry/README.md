# Internal registry

> Phase 05 · Builds and images · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- The integrated image registry and its operator
- Exposing the registry route and pushing with Podman
- Pull access across projects (`system:image-puller`)
- Registry storage

## 🧩 Key ideas

- **Internal registry** — A registry running inside the cluster, integrated with ImageStreams and RBAC.

## 🔀 OpenShift vs plain Kubernetes

Plain Kubernetes ships no registry.

## 🍔 Zomato app tie-in

Push your own order-service image into CRC's registry and deploy from it.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Registry](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
