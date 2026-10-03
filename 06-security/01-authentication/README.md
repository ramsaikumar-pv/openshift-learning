# Authentication

> Phase 06 · Security · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- The OpenShift OAuth server and identity providers
- kubeadmin and why to remove it
- Configure an htpasswd identity provider
- Users, Identities and Groups objects

## 🧩 Key ideas

- **Identity provider** — Where OpenShift checks passwords: htpasswd, LDAP, OIDC (e.g. Keycloak / Entra ID)…

## 🔀 OpenShift vs plain Kubernetes

Plain Kubernetes has no built-in user login; OpenShift ships an OAuth server.

## 🍔 Zomato app tie-in

Create users for a dev and an ops person on CRC.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Authentication and authorization](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
