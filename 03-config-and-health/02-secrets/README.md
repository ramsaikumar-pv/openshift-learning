# Secrets

> Phase 03 · Config and health · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Secret types: Opaque, dockerconfigjson, tls, service-account token
- base64 is encoding, not encryption
- Consume as env vars and as files
- Image pull secrets
- etcd encryption and external secret stores (concepts)

## 🧩 Key ideas

- **Secret** — Like a ConfigMap but meant for sensitive data: kept out of logs, tmpfs-mounted, and access-controlled by RBAC.
- **Real protection** — RBAC (who can read), etcd encryption at rest, and keeping secrets out of Git (Sealed Secrets / External Secrets in Phase 9).

## 🔀 OpenShift vs plain Kubernetes

OpenShift supports etcd encryption (admin-enabled) and the Secrets Store CSI driver / External Secrets Operator — availability is version-dependent.

## 🍔 Zomato app tie-in

Store the payment gateway API key (fake!) and DB password as Secrets.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
