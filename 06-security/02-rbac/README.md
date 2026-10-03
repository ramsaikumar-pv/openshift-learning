# RBAC

> Phase 06 · Security · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Role vs ClusterRole, RoleBinding vs ClusterRoleBinding
- Default roles: view, edit, admin, cluster-admin
- `oc adm policy add-role-to-user`, `oc auth can-i`, `oc auth can-i --as`
- Least privilege in practice

## 🧩 Key ideas

- **RBAC** — Verbs (get, create…) on resources (pods, secrets…), granted to users/groups/serviceaccounts. Allow-only; no deny rules.

## 🍔 Zomato app tie-in

The dev can edit zomato-dev and only view zomato-prod.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)
- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
